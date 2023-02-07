# ejercicioUseReducer

#useReducer
import React, { useReducer } from "react";

import Button from "../../../components/Button";

const counterReducer = (state, event) => {
  switch (event) {
    case "suma":
      return { ...state, count: state.count + 1 };
    case "resta":
      return { ...state, count: state.count - 1 };
    default:
      return state;
  }
};

export default function ReducerSection() {
  const [state, dispatch] = useReducer(counterReducer, { count: 0 });
  return (
    <div className="flex-center flex-column">
      <h3>useReducer</h3>
      <div className="flex-center flex-column">
        <span>{state.count}</span>
        <div>
          <Button onClick={() => dispatch("resta")}>-</Button>
          <Button onClick={() => dispatch("suma")}>+</Button>
        </div>
      </div>
    </div>
  );
}


#useState
import React, { useState } from "react";

export default function ContextSection() {
  const [contador, setContador] = useState(0);

  return (
    <div className="flex-center flex-column">
      <h3>useSate</h3>
      <div className="flex-center flex-column">
        <span>{contador}</span>
        <div>
          <button
            className="app-button"
            onClick={() => setContador(contador - 1)}
          >
            -
          </button>
          <button
            className="app-button"
            onClick={() => setContador(contador + 10)}
          >
            +
          </button>
        </div>
      </div>
    </div>
  );
}
