`SignInTests.cs`
{:.file-name}

```cs
using Atata;
using NUnit.Framework;

namespace AtataDemo.UITests
{
    [TestFixture]
    public class SignInTests : UITestFixture
    {
        [Test]
        public void SignIn()
        {
            Go.To<SignInPage>()
                .Email.Set("admin@mail.com")
                .Password.Set("abc123")
                .SignIn.Click();
        }
    }
}
```
{:.test}