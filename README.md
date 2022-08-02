# components
## Images
![IMG20220802131738](https://user-images.githubusercontent.com/101010104/182321427-3a7ec6d5-acf1-48e0-8ada-f14fa2c57f3b.jpg)
Explaination PART of UseSate and Props Using:
Import all File in App.js

import React from "react";
import Game from "./components/Game";

const App = () => <Game />;

export default App;


Create One  Component name Game.jsx and Destructuring Props
const  Game= (props) => (
	<button onClick={props.onClick}>{props.value}</button>
);

Create States and Fill with Initial Data

We begin by adding a hook called usedState in Game.js and creating states to set an empty board and specify the next player. Lastly, we add const winner, which tells us whether the latest move was a winning one:

const [board, setBoard] = useState(Array(9).fill(null));
const [xIsNext, setXisNext] = useState(true);
const winner = calculateWinner(board);

Create the handleClick Function

const handleClick = (i) => {
	const boardCopy = [...board];
	// If user click an occupied square or if game is won, return
	if (winner || boardCopy[i]) return;
	// Put an X or an O in the clicked square
	boardCopy[i] = xIsNext ? "X" : "O";
	setBoard(boardCopy);
	setXisNext(!xIsNext);
};



