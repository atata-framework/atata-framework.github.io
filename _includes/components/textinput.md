<p class="lead">Represents the text input control. Handles any input with type="text" or without type attribute defined.</p>

```html
<input type="text" id="first-name">
```
```cs
using _ = SampleApp.SamplePage;

namespace SampleApp
{
    public class SamplePage : Page<_>
    {
        [FindById]
        public TextInput<_> FirstName { get; private set; }
    }
}
```
```cs
Go.To<SamplePage>().
    FirstName.Set("some text").
    FirstName.Should.Equal("some text");
```