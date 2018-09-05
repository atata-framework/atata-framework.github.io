Represents the text area control. 
Default search is performed by the label.

```html
<textarea name="description">
</textarea>
```
```cs
using Atata;
using _ = SampleApp.SamplePage;

namespace SampleApp
{
    public class SamplePage : Page<_>
    {
        [FindByName]
        public TextArea<_> Description { get; private set; }
    }
}
```
```cs
Go.To<SamplePage>().
    Description.Set("some").
    Description.Append(" text").
    Description.Should.Equal("some text");
```

Supports `[Format]` and `[RandomizeStringSettings]` settings attributes.
{:class="info"}