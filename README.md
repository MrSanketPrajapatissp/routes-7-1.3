# Context API

Output of the code: 

![Screenshot (472)](https://github.com/user-attachments/assets/e8336cab-919d-490a-a915-2f5776d0b59f)




## code for Context API below is App.jsx file

```import { useContext, useState } from "react";
import { CountContext } from "./context";

function App() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <CountContext.Provider value={count}>
        <Count setCount={setCount} />
      </CountContext.Provider>
    </div>
  );
}

function Count({ setCount }) {
  return (
    <div>
      <CountRenderer />
      <Buttons setCount={setCount}></Buttons>
    </div>
  );
}

function CountRenderer() {
  const count = useContext(CountContext);

  return <div>{count}</div>;
}

function Buttons({ setCount }) {
  const count = useContext(CountContext);

  return (
    <div>
      <button
        onClick={function () {
          setCount(count + 1);
        }}
      >
        {" "}
        Incresae
      </button>
      <button
        onClick={function () {
          setCount(count - 1);
        }}
      >
        {" "}
        Decrease
      </button>
    </div>
  );
}
export default App;

```


## context.jsx 
```
import { createContext } from "react";

export const CountContext = createContext(0);

````
## Contributing

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.
