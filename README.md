import flet as ft
 
def main(page: ft.Page):
 
    r = 255
    g = 0
    b = 0
 
    #Functions
    def rgb_to_hex(r, g, b):
        return f"#{r:02x}{g:02x}{b:02x}"
   
    def update_color(e):
        nonlocal r, g, b
        r = int(slider1.value)
        g = int(slider2.value)
        b = int(slider3.value)
 
        boxcolor.bgcolor = rgb_to_hex(r, g, b)
 
    #Main Page
    page.vertical_alignment = ft.MainAxisAlignment.CENTER
    page.horizontal_alignment = ft.CrossAxisAlignment.CENTER
 
    #Controls
    slider1 = ft.Slider(label="Slider", value = 0, max = 255, on_change = update_color)
    slider2 = ft.Slider(label="Slider", value = 0, max = 255, on_change = update_color)
    slider3 = ft.Slider(label="Slider", value = 0, max = 255, on_change = update_color)
    boxcolor = ft.Container(width = 150, height = 150)
    message = ft.Text()
 
    page.add(slider1, slider2, slider3, message, boxcolor)
ft.run(main = main)
