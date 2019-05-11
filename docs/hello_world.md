**Hello World** application requests user's name and greets them.

# Source Code

```
from fase import fase


class HelloWorldService(fase.Service):

  def OnStart(self):
    screen = fase.Screen(self)
    screen.AddText(id_='text_name_id', hint='Enter Name')
    screen.AddButton(id_='next_button_id', text='Next',
                     on_click=HelloWorldService.OnNextButton)
    return screen

  def OnNextButton(self, screen, element):
    name = screen.GetText(id_='text_name_id').GetText()
    screen = fase.Screen(self)
    screen.AddLabel(id_='hello_label_id', text='Hello, %s!' % name)
    screen.AddButton(id_='reset_button_id', text='Reset',
                     on_click=HelloWorldService.OnResetButton)
    return screen
    
  def OnResetButton(self, screen, element):
    # Ignore previous screen and element.
    return self.OnStart()


fase.Service.RegisterService(HelloWorldService)
```

# Screenshots

## iOS

<img alt='Hello World Initial' src='../images/hello_world_ios/initial.png' width='300' height='533'>
<img alt='Hello World Hello' src='../images/hello_world_ios/greeting.png' width='300' height='533'>

## Android

<img alt='Hello World Initial' src='../images/hello_world_android/initial.png' width='300' height='533'>
<img alt='Hello World Hello' src='../images/hello_world_android/greeting.png' width='300' height='533'>
