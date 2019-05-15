# Create Service
  * Create file `service.py`;
  * Import `fase` module with Fase Elements and define `ConverterService` as child of `fase.Service`;
  * Create method `OnStart(self)` and the rest of the Application:

```
from fase_lib import fase

LB_KG=0.45359237


class ConverterService(fase.Service):

  def OnStart(self):
    # Create a new screen with basic control elements.
    screen = fase.Screen(self)
    # Set screen title. 
    screen.SetTitle('Converter')
    # Add Text field to enter value.
    screen.AddText(id_='enter_weight_text_id', hint='Enter Weight', type_=fase.Text.DIGITS)
    # Add Selector to let user choose between lg and lbs.
    screen.AddSelect(id_='select_weight_unit_id', items=['kg', 'lbs'], hint='Select unit')
    # Add Button and pass it a callback.
    screen.AddButton(id_='convert_weight_button_id', text='Convert', on_click=ConverterService.OnConvertWeightButton)
    return screen
  
  def OnConvertWeightButton(self, screen, element):
    # Callback receives screen and element where callback was generated.
    # Argument screen is screen where button was clicked.
    # Argument element is the button which was clicked.
    # If kg was selected, convert value to lbs and vise versa.
    if screen.GetSelect(id_='select_weight_unit_id').GetValue() == 'kg':
      kg = float(screen.GetText(id_='enter_weight_text_id').GetText())
      lbs = kg / LB_KG
      output_label = '%f kg is %f lbs' % (kg, lbs)
    else:
      lbs = float(screen.GetText(id_='enter_weight_text_id').GetText())
      kg = lbs * LB_KG
      output_label = '%f lbs is %f kg' % (lbs, kg)
    # Create a new screen with output information.
    screen = fase.Screen(self)
    screen.AddLabel(id_='output_label_id', text=output_label)
    # Add button which resets app.
    screen.AddButton(id_='reset_button_id', text='Reset', on_click=ConverterService.OnResetButton)
    return screen

  def OnResetButton(self, screen, element):
    # Ignore previous screen and element.
    return self.OnStart()
```
