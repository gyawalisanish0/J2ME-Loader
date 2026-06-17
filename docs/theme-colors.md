# Theme Color Reference

## Button / Brand Color

The app uses a single color for all action buttons (PRESETS, KEY MAPPINGS, etc.):

```xml
@color/btn_bg_normal
```

| Mode | Value | Looks like |
|------|-------|------------|
| Light | `#2e2e2e` | near-black |
| Dark  | `#0099ff` | blue |

Defined in:
- `app/src/main/res/values/colors.xml` — light
- `app/src/main/res/values-night/colors.xml` — dark

Android picks the right one automatically based on system night mode.

## How to Use in Java

```java
import androidx.core.content.ContextCompat;

int color = ContextCompat.getColor(context, R.color.btn_bg_normal);
```

For colored text (e.g. a menu item label):

```java
SpannableString label = new SpannableString(getString(R.string.edit));
label.setSpan(new ForegroundColorSpan(ContextCompat.getColor(this, R.color.btn_bg_normal)),
        0, label.length(), 0);
menu.add(0, 0, 0, label);
```

## Other Theme Colors

| Resource | Light | Dark | Used for |
|----------|-------|------|----------|
| `@color/primary` | `#212121` | `#262e37` | Action bar, `colorPrimary` |
| `@color/accent` | `#ff2e51` | `#0099ff` | `colorAccent`, image button tint |
| `@color/background` | `#fafafa` | `#20272f` | Window/card background |
| `@color/text_primary` | `#000000` | `#ffffff` | Body text |
| `@color/text_secondary` | `#353535` | `#dedede` | Secondary text, switch labels |

## Key Style Attributes

- `?attr/textColorPrimary` — primary text color (theme-aware)
- `?attr/textColorSecondary` — secondary text color (theme-aware)
- `?attr/colorAccent` — accent/tint color (image buttons, file picker)
- `?attr/colorControlNormal` — icon tint for controls (pencil icon uses this)

## Button Style

Buttons use `ButtonStyle` in `styles.xml`:

```xml
<style name="ButtonStyle" parent="Widget.AppCompat.Button.Colored">
    <item name="android:background">@drawable/bg_button</item>
</style>
```

`bg_button.xml` is a shape selector using `@color/btn_bg_normal` (normal) and
`@color/btn_bg_pressed` (pressed state).
