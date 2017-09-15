#!/usr/bin/env python
 
import screenlets
 
class HelloWorldScreenlet(screenlets.Screenlet):
    __name__ = 'HelloWorld'
    __version__ = '0.1'
    __author__ = 'John Doe'
    __desc__ = 'Simple Hello World Screenlet'
     
    def __init__(self, **kwargs):
        # Customize the width and height.
        screenlets.Screenlet.__init__(self, width=180, height=50, **kwargs)
     
    def on_draw(self, ctx):
        # Change the color to white and fill the screenlet.
        ctx.set_source_rgb(255, 255, 255)
        self.draw_rectangle(ctx, 0, 0, self.width, self.height)
 
        # Change the color to black and write the message.
        ctx.set_source_rgb(0, 0, 0)
        text = 'Hello World!'
        self.draw_text(ctx, text, 10, 10, "Sans 9" , 20, self.width)
 
 
if __name__ == "__main__":
    import screenlets.session
    screenlets.session.create_session(HelloWorldScreenlet)