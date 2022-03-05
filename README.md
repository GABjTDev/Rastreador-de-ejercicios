# [Exercise Tracker](https://www.freecodecamp.org/learn/apis-and-microservices/apis-and-microservices-projects/exercise-tracker)

```js
import { Progress } from '@chakra-ui/react'
const ProgressLinear = ({value}) => {
  return (
    <Progress value={value} />
  )
}
export default ProgressLinear
```

Implementacion del componente progreso linear
```js
import ProgressLinear from "../Progress/ProgressLinear";
import { useEffect, useState } from "react";
const Example = () => {
    const [value, setValue] = useState(0);
    useEffect(() => {
    const updateValue = () => {
        setValue(val => val + 1)
    }
    if(value < 100){
        setTimeout(updateValue, 10)
    }else{
        clearTimeout(updateValue)
    }
    }, [value])
    return (
    <>
        {
            value < 100 ?
                <ProgressLinear value={value} />
            :
                <h1>Cargado</h1>
        }
    </>
}
```
