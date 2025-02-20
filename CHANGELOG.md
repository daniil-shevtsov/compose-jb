# 1.0.0-alpha (Aug 2021)
## Common
- Desktop, Web, and Android artifacts publish at the same time with the same version

## Desktop

### Features
- [Context menu support in selectable text](https://android-review.googlesource.com/c/platform/frameworks/support/+/1742314)
- [Cursor change behavior in text and pointer icon API](https://android-review.googlesource.com/c/platform/frameworks/support/+/1736714/12/compose/desktop/desktop/samples/src/jvmMain/kotlin/androidx/compose/desktop/examples/example1/Main.jvm.kt#357)
- [Mouse Clickable modifier](https://github.com/JetBrains/compose-jb/tree/master/tutorials/Mouse_Events#mouse-rightmiddle-clicks-and-keyboard-modifiers)
- Tab navigation between text fields by default
- Resource packing to native distribution
- Support @Preview annotation in desktopMain sourceSet's (when the Compose MPP plugin is installed in IDEA)
- [New features for Composable menu (icons, shortcuts, mnemonics, radiob buttons, checkboxes](https://github.com/JetBrains/compose-jb/tree/master/tutorials/Tray_Notifications_MenuBar_new#menubar)
- [Adaptive window size](https://github.com/JetBrains/compose-jb/blob/master/tutorials/Window_API_new/README.md#adaptive-window-size)
- Support Linux on ARM64
- [Support hidpi on some Linux distros](https://github.com/JetBrains/compose-jb/issues/188#issuecomment-891614869)
- Support resizing of undecorated resizable windows (`Window(undecorated=true, resizable=true, ...)`)

### API changes
- new Window API is no longer experimental
- old Window API is deprecated
- classes from `android.compose.desktop.*` moved to `androidx.compose.ui.awt.*` (ComposeWindow, ComposePanel, etc)
- `svgResource`/`vectorXmlResource`/`imageResource` replaced by painterResource

### API breaking changes:
- Window level keyboard API for the old Window API removed
- Window(icon: BufferedImage) replaced by Window(icon: Painter)
- ContextMenu renamed to CursorDropdownMenu

## Web

### API changes
- [classes behave cumulatively](https://github.com/JetBrains/compose-jb/pull/690)
- [removed content builder for empty elements](https://github.com/JetBrains/compose-jb/issues/744)
- [Introduce CSS arithmetic operations](https://github.com/JetBrains/compose-jb/pull/761)
- [Improved the types of Inputs and input events](https://github.com/JetBrains/compose-jb/pull/799)
- [All event types expose native properties](https://github.com/JetBrains/compose-jb/pull/887)
- [Added a complete list of HTML color aliases](https://github.com/JetBrains/compose-jb/issues/890)
- [Introduce support for CSS Grid API](https://github.com/JetBrains/compose-jb/issues/895)
- [Deprecate Color.RGB, Color.HSL etc. functions in favor of top-level rgb, hsl an so on](https://github.com/JetBrains/compose-jb/issues/902)
- [negate CSSNumeric value directly](https://github.com/JetBrains/compose-jb/issues/921)

### API breaking changes
- [boolean like attributes don't have any parameters anymore](https://github.com/JetBrains/compose-jb/pull/780)
- [removed input type specific event listeners](https://github.com/JetBrains/compose-jb/pull/861)
- [replaced maxWidth/minWidth media queries with prefixed names](https://github.com/JetBrains/compose-jb/issues/886)
- [Remove CSSVariables context and introduce specialized methods for adding String- and Number-valued CSS variables](https://github.com/JetBrains/compose-jb/issues/894)
- [inline style builder was moved into AttributeBuilder scope](https://github.com/JetBrains/compose-jb/pull/699)


# M4 (Jun 2021)
  * New experimental [Composable Window API](https://github.com/JetBrains/compose-jb/tree/master/tutorials/Window_API_new)
  * [Tooltips](https://github.com/JetBrains/compose-jb/tree/master/tutorials/Desktop_Components#tooltips)
  * Use [Metal renderer for macOS by default](https://github.com/JetBrains/skiko/pull/70)
  * [Expose a swing mouse event in Modifier.pointerInput](https://github.com/JetBrains/compose-jb/issues/129#issuecomment-784149646)
  * Improved [keyboard support in TextField](https://android-review.googlesource.com/c/platform/frameworks/support/+/1578803)
  * Avoid forcing discrete GPU on multi-GPU MacOS machines in [Skiko](https://github.com/JetBrains/skiko/pull/83) and [native distributions](https://github.com/JetBrains/compose-jb/issues/545)
  * [Make DropdownMenu focusable by default](https://github.com/JetBrains/compose-jb/issues/375)
  * [Scrollbar. get rid of itemCount and averageItemSize from rememberScrollbarAdapte](https://github.com/JetBrains/compose-jb/issues/181)
  * [Support scrollbars for LazyColumn with reverseLayout = true](https://github.com/JetBrains/compose-jb/issues/209)
  * Fix [memory leak](https://github.com/JetBrains/compose-jb/issues/538)
  * Fix [Scroll NaN rounding bug, desktop version](https://github.com/JetBrains/compose-jb/issues/304)
  * Fix [Dragging prevents pointer move events](https://github.com/JetBrains/compose-jb/issues/134)
  * Fix [Dragging window to another display makes Icon show up incorrectly](https://github.com/JetBrains/compose-jb/issues/677)
  * Fix ["Padding must be non-negative" after resizing window with Slider and Box](https://github.com/JetBrains/compose-jb/issues/367)
  * Breaking change [old Dialog/Menubar/Tray are moved to androidx.compose.ui.window.v1](https://android-review.googlesource.com/c/platform/frameworks/support/+/1685905)

# M3 (Feb 2021)
   * Improve [TextField](https://github.com/JetBrains/compose-jb/issues/277)
   * Support [SVG](https://github.com/JetBrains/compose-jb/tree/master/tutorials/Image_And_Icons_Manipulations#loading-svg-images)
   * Support [vsync](https://github.com/JetBrains/skiko/pull/44),  [sync composition with rendering frames](https://android-review.googlesource.com/c/platform/frameworks/support/+/1534675)
   * Support [DirectX on Windows by default](https://github.com/JetBrains/skiko/pull/63)
   * Support [software rendering fallback](https://github.com/JetBrains/skiko/pull/56)
   * Implement [signing and notarization for macOS](https://github.com/JetBrains/compose-jb/tree/master/tutorials/Signing_and_notarization_on_macOS)
   * Improve Swing interoperability support [Swing component in Compose hierarchy](https://github.com/JetBrains/compose-jb/tree/master/tutorials/Swing_Integration#adding-a-swing-component-to-cfd-composition-using-swingpanel)
   * Support using [Compose in IntelliJ plugins](https://github.com/JetBrains/compose-jb/tree/master/examples/intelliJPlugin)
   * Skiko native binaries are now signed on macOS (x64 and arm)
   * Fix [Ambients are not transferred across pop ups](https://github.com/JetBrains/compose-jb/issues/135)
   * Fix [Laggy UI on Linux](https://github.com/JetBrains/compose-jb/issues/23)
   * Fix [Using AndroidX Compose specific dependencies for Android target](https://github.com/JetBrains/compose-jb/issues/272)

# M2 (Dec 2020)
   * Swing interoperability support (Compose in Swing frame)
   * Support [XML vector images](https://developer.android.com/guide/topics/graphics/vector-drawable-resources)
   * [Support for Gradle 6.6 and 6.7](https://github.com/JetBrains/compose-jb/issues/66)
   * [Support macOS 10.13 and 10.14](https://github.com/JetBrains/compose-jb/issues/76)
   * Support Apple Silicon (arm64) natively
   * [Support letter spacing in text](https://github.com/JetBrains/compose-jb/issues/82)
   * [Implemented desktop "ActualDialog" and "ActualPopup"](https://github.com/JetBrains/compose-jb/issues/19)
   * [Fix input method bar positioning](https://github.com/JetBrains/compose-jb/issues/67)
   * [Fix text alignment](https://github.com/JetBrains/compose-jb/issues/92)
   * [Fix dropdown/popup positioning](https://github.com/JetBrains/compose-jb/issues/139)
   * [Fix using with Compose in same app as Java FX](https://github.com/JetBrains/compose-jb/issues/17)
   * [Added screenshots of example apps](https://github.com/JetBrains/compose-jb/issues/90)

# M1 (Nov 2020)
   * Initial release
