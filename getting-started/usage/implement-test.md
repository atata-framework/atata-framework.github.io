The following sample uses additional [NUnit](https://www.nuget.org/packages/NUnit/) and [ChromeDriver](https://www.nuget.org/packages/WebDriver.ChromeDriver.win32/) NuGet packages.
{:.warning}

`SignInTests.cs`
{:.file-name}

```cs
using Atata;
using NUnit.Framework;

namespace SampleApp.UITests
{
    [TestFixture]
    public class SignInTests
    {
        [SetUp]
        public void SetUp()
        {
            AtataContext.Configure().
                UseChrome().
                UseBaseUrl("https://atata-framework.github.io/atata-sample-app/#!/").
                UseNUnitTestName().
                AddNUnitTestContextLogging().
                AddScreenshotFileSaving().
                LogNUnitError().
                TakeScreenshotOnNUnitError().
                Build();
        }

        [TearDown]
        public void TearDown()
        {
            AtataContext.Current?.CleanUp();
        }

        [Test]
        public void SignIn()
        {
            Go.To<SignInPage>().
                Email.Set("admin@mail.com").
                Password.Set("abc123").
                SignIn.Click();
        }
    }
}
```
{:.test}