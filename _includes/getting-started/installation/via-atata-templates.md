To get started install [**Atata Templates**]({{ site.links.atata_templates }}) Visual Studio extension.

The extension provides the following templates:

- Project templates:
  - Atata NUnit Basic Test Project (.NET Core)
  - Atata NUnit Basic Test Project (.NET Framework)
  - Atata NUnit Advanced Test Project (.NET Core)
  - Atata Components Library (.NET Standard)
  - Atata Components Library (.NET Framework)
- Item templates:
  - Atata Page Object
  - Atata Base Page Object
  - Atata Control
  - Atata Trigger
  - Atata NUnit Test Fixture
  - Atata NUnit Base Test Fixture

When extension is installed, you can create a project of one of Atata project types. In Visual Studio:

1. Go to **File/New/Project...**
1. Select **Installed/Visual C#/Atata** category
1. Choose template (e.g.: **Atata NUnit Advanced Test Project (.NET Core)**) and specify project name and location

![Atata Templates project](/assets/images/atata-templates/new-project-window.png?v3)

The project is created with NuGet package references:

- {% include nuget.md name="Atata" %}
- {% include nuget.md name="Atata.WebDriverExtras" %}
- {% include nuget.md name="Selenium.WebDriver" %}
- {% include nuget.md name="NUnit" %}
- {% include nuget.md name="NUnit3TestAdapter" %}

You might also need to install a driver package for specific browser: {% include nuget.md name="Selenium.WebDriver.ChromeDriver" %}, {% include nuget.md name="Selenium.WebDriver.IEDriver" %}, etc.
{:.warning}

In the created project you can specify your testing site base URL and apropriate driver in `UITestFixture.cs` class, e.g.:

```cs
AtataContext.Configure()
    .UseChrome()
    .UseBaseUrl("SITE_URL")
    //...
```

Further test fixture classes are recommended to inherit from `UITestFixture`, or just choose "Atata NUnit Test Fixture" item template in "Add New Item Window".