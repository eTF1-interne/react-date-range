This component extends all the props of **[Calendar](#calendar)** component. In addition to those props, it has the following props: 

| Prop Name                         | Type     |
| --------------------------------- | -------- |
| **moveRangeOnFirstSelection**     | boolean  |
| **retainEndDateOnFirstSelection** | boolean  |
| **onRangeFocusChange**            | function |
| **rangeColors**                   | array    |
| **ranges**                        | array    |


#### Example: Editable Date Inputs
```jsx inside Markdown
import {useState} from 'react'
import { fr } from 'date-fns/locale'
import { startOfDay } from 'date-fns'


const now = startOfDay(new Date())

const [state, setState] = useState([
    {
      startDate: new Date(),
      endDate: null,
      key: 'selection'
    }
  ]);
  
<DateRange
  direction="horizontal"
  locale={fr}
  months={2}
  dateDisplayFormat="dd/MM/yyyy"
  minDate={now}
  startDatePlaceholder="Saisir la date de début"
  endDatePlaceholder="Saisir la date de fin"
  editableDateInputs={true}
  onChange={item => setState([item.selection])}
  moveRangeOnFirstSelection={false}
  ranges={state}
/>

```
