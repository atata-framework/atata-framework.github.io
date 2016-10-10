Specifies the verification of the page content. Verifies whether the component contains the specified content values. By default occurs during the page object initialization.

```cs
[VerifyContent("Some text", "Another text")]
public class SamplePage : Page<_>
{
}
```

The example verifies that the page content should contain text: "Some text" and "Another text".
{:.info}