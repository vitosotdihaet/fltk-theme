# fltk-theme

A theming crate for fltk-rs, based on work by [Greg Ercolano](https://groups.google.com/g/fltkgeneral/c/3A5VC_854ok/m/sDpJsmuLBAAJ).

## Usage
```toml
[dependencies]
fltk = "1.1.3"
fltk-theme = "0.1"
```

## Example
```rust
use fltk::{prelude::*, *};
use fltk_theme::Theme;

fn main() {
    let a = app::App::default().with_scheme(app::Scheme::Gtk);
    let theme = Theme::load("examples/dark.map").unwrap();
    theme.select();
    let mut win = window::Window::default().with_size(400, 300);
    let mut btn = button::Button::new(160, 200, 80, 40, "Hello");
    btn.set_color(btn.color().lighter());
    win.end();
    win.show();
    a.run().unwrap();
}
```