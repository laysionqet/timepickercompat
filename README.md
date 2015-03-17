# timepickercompat
Material style of timepicker for pre-Lollipop, scratched from android app DesktopClock and modified by laysionqet

## usage
- property configing
  - multi-color(not dark mode)
  ```java
            TimePickerDialog dialog new TimePickerDialog.Builder()
                  .setPrimaryColor(primaryColor)
                  .setPrimaryColorDark(primaryColorDark)
                  .setSelectedColor(selectedColor)
                  .setUnselectedColor(unselectedColor)
                  .setOnTimeSetListener(timeSetListener)
                  .setHourOfDay(calendar.get(Calendar.HOUR_OF_DAY))
                  .setMinute(calendar.get(Calendar.MINUTE))
                  .setIs24HourMode(is24HourMode)
                  .create();
  ```
                  
  - darkmode
  ```java
              TimePickerDialog dialog new TimePickerDialog.Builder()
                  .setThemeDark(true)
                  .setOnTimeSetListener(timeSetListener)
                  .setHourOfDay(calendar.get(Calendar.HOUR_OF_DAY))
                  .setMinute(calendar.get(Calendar.MINUTE))
                  .setIs24HourMode(is24HourMode)
                  .create();
  ```
                  
- showing timepicker dialog
  ```java
        FragmentManager manager = getActivity().getFragmentManager();
        // Make sure the dialog isn't already added.
        manager.executePendingTransactions();
        final FragmentTransaction ft = manager.beginTransaction();
        final Fragment prev = manager.findFragmentByTag(FRAG_TAG_TIME_PICKER);
        if (prev != null) {
            ft.remove(prev);
        }
        ft.commit();

        if (dialog != null && !dialog.isAdded()) {
            dialog.show(manager, FRAG_TAG_TIME_PICKER);
        }
  ```
