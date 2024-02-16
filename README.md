# accending-decending-reset
import "./styles.css";
import { useState } from "react";

export default function App() {
  let numbers = [5, 3, 8, 1, 2, 9, 4, 7, 6];
  const [accended, setAccended] = useState([5, 3, 8, 1, 2, 9, 4, 7, 6]);

  function accending() {
    setAccended(numbers.slice().sort((a, b) => a - b));
  }
  function dccending() {
    setAccended(numbers.slice().sort((a, b) => b - a));
  }
  function reset() {
    setAccended(numbers);
  }
  return (
    <div className="App">
      {accended.map((accended, index) => (
        <div key={index}>{accended}</div>
      ))}
      <button onClick={accending}>Accending</button>
      <button onClick={dccending}>Dccending</button>

      <button onClick={reset}> Reset</button>
    </div>
  );
}
