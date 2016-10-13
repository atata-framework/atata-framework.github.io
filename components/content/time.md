Represents any element containing time content. Default search is performed by the label.

```html
<span id="time-of-day">2:45 PM</span>
```
```cs
using Atata;
using _ = SampleApp.SamplePage;

namespace SampleApp
{
    public class SamplePage : Page<_>
    {
        [FindById]
        [Format("h:mm tt")]
        public Time<_> TimeOfDay { get; private set; }
    }
}
```
```cs
Go.To<SamplePage>().
    TimeOfDay.Should.Equal(new TimeSpan(14, 45, 0));
```

Supports `[Format]` and `[Culture]` settings attributes.
{:.info}