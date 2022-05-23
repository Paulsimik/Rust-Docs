# Colors
|Name|RGBA|HEX|
|:---:|:---:|:---:|
|Red|0.8 0.28 0.2 1|cd4632|
|Green|0.55 0.78 0.24 1|8cc83c|
|Blue|0.204 0.596 0.859 1|3498db|

# Fonts
|Name|
|:---|
|assets/content/ui/fonts/droidsansmono.ttf|
|assets/content/ui/fonts/permanentmarker.ttf|
|assets/content/ui/fonts/robotocondensed-bold.ttf|
|assets/content/ui/fonts/robotocondensed-regular.ttf|

# Classes
```ruby
static public CuiElementContainer CreateElementContainer(string panelName, string color, string material, float fadeIn, float fadeOut, string aMin, string aMax, bool useCursor = false, string parent = "Overlay")
            {
                var element = new CuiElementContainer()
                {
                    {
                        new CuiPanel
                        {
                            Image = { Color = color, Material = material, FadeIn = fadeIn },
                            RectTransform = { AnchorMin = aMin, AnchorMax = aMax },
                            FadeOut = fadeOut,
                            CursorEnabled = useCursor
                        },
                        new CuiElement().Parent = parent,
                        panelName
                    }
                };
                return element;
            }
```       
```ruby
static public void CreateLabel(ref CuiElementContainer container, string panel, string color, float fadeIn, float fadeOut, string text, int size, string aMin, string aMax, TextAnchor align = TextAnchor.MiddleCenter)
            {
                container.Add(new CuiLabel
                {
                    Text = { Color = color, FontSize = size, Align = align, Text = text, FadeIn = fadeIn },
                    RectTransform = { AnchorMin = aMin, AnchorMax = aMax },
                    FadeOut = fadeOut
                },
                panel);

            }
```
```ruby
static public void CreateButton(ref CuiElementContainer container, string panel, string color, float fadeIn, float fadeOut, string text, int size, string aMin, string aMax, string command, TextAnchor align = TextAnchor.MiddleCenter)
            {
                container.Add(new CuiButton
                {
                    Button = { Color = color, Command = command, FadeIn = fadeIn },
                    RectTransform = { AnchorMin = aMin, AnchorMax = aMax },
                    Text = { Text = text, FontSize = size, Align = align, FadeIn = fadeIn },
                    FadeOut= fadeOut
                },
                panel);
            }
```
