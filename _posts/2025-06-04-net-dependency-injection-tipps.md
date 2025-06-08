---
title: "Dependency Injection in .NET: Tipps aus der Praxis"
date: 2025-06-04
author: Michael
categories: [.NET, Architektur]
tags: [dependency-injection, .net, best-practices]
excerpt: "Praktische Hinweise zur sauberen Nutzung von Dependency Injection in .NET-Projekten"
---

Dependency Injection (DI) gehört zu den Grundpfeilern moderner .NET-Architektur. Dennoch sehe ich in vielen Projekten typische Fehler oder Missverständnisse – vom übermäßigen Einsatz des Service Locators bis hin zur fehlenden Trennung von Lebenszyklen.

In diesem Beitrag zeige ich dir konkrete Tipps und Codebeispiele, wie du DI in .NET sauber, effizient und wartbar einsetzt – mit einem Blick auf reale Szenarien aus langjähriger Projektpraxis.

## 1. Constructor Injection bevorzugen

Nutze Constructor Injection, wann immer möglich. Sie ist explizit, testbar und klar strukturiert:

```csharp
public class MyService
{
    private readonly ILogger<MyService> _logger;
    private readonly IRepository _repository;

    public MyService(ILogger<MyService> logger, IRepository repository)
    {
        _logger = logger;
        _repository = repository;
    }

    public void DoWork() => _logger.LogInformation("Working...");
}
```


## 2. Services korrekt registrieren

Achte auf den Lebenszyklus deiner Services – Scoped, Transient und Singleton bedeuten unterschiedliche Dinge:

```csharp
services.AddScoped<IRepository, SqlRepository>();
```

## 3. Vermeide den Service Locator

Vermeide Muster wie:

```csharp
var service = serviceProvider.GetService<IMyService>();
```

## 4. Fazit

Dependency Injection ist mächtig – aber nur so gut wie ihr Einsatz. Mit einem klaren Fokus auf Konstruktor-Injektion, korrekter Registrierung und expliziten Abhängigkeiten wird dein Code robuster und wartbarer. 
Du hast eigene Erfahrungen mit DI in .NET gemacht? Teile sie gern in den Kommentaren!