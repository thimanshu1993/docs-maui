---
title: "Bind a Java library"
description: "Learn about how to bind a Java library for use in a .NET MAUI Android app."
ms.date: 06/05/2023
---

# Bind a Java library

There's a large third-party library ecosystem for Android, and .NET for Android offers multiple approaches for using these libraries:

- Re-use Java code by including it in your project, and optionally generate a C# API for it.
- Create a *bindings library* that automatically wraps the library with C# wrappers so that you can invoke Java code via C# calls.
- Use the *Java Native Interface (JNI)* to invoke calls in Java library code directly. JNI is a framework that enables Java code to call and be called by native apps or libraries.

.NET for Android implements bindings by using *Managed Callable Wrappers (MCW)*. MCW is a JNI bridge that's used when managed code needs to invoke Java code. Managed callable wrappers also provide support for subclassing Java types and for overriding virtual methods on Java types. Similarly, whenever Android runtime (ART) code wants to invoke managed code, it does so via another JNI bridge known as Android Callable Wrappers (ACW). This architecture is shown in the following diagram:

:::image type="content" source="media/architecture.png" alt-text="Architecture diagram for how .NET for Android invokes Java code." border="false":::

----


Troubleshooting Android Bindings - https://github.com/xamarin/java.interop/wiki/Troubleshooting-Android-Bindings-Issues
Investigate/document slim bindings - https://github.com/xamarin/xamarin-android/issues/7369
Add support for AndroidJavaSource to Bindings - https://github.com/xamarin/xamarin-android/pull/5926
