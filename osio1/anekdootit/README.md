
App.js

import { useState } from 'react'

const App = () => {
  const anecdotes = [
    'If it hurts, do it more often.',
    'Adding manpower to a late software project makes it later!',
    'The first 90 percent of the code accounts for the first 90 percent of the development time...The remaining 10 percent of the code accounts for the other 90 percent of the development time.',
    'Any fool can write code that a computer can understand. Good programmers write code that humans can understand.',
    'Premature optimization is the root of all evil.',
    'Debugging is twice as hard as writing the code in the first place. Therefore, if you write the code as cleverly as possible, you are, by definition, not smart enough to debug it.',
    'Programming without an extremely heavy use of console.log is same as if a doctor would refuse to use x-rays or blood tests when dianosing patients.'
  ]
   
  const [selected, setSelected] = useState(0)
  const [points, setPoints] = useState(new Uint8Array(7))
 // const [popular, setPopular] = useState(0)
  

  //new Uint8Array(7); 
  //const testArray =[];
  //const copy = { ...points }


  
 

  //const randomI = [getRandomInt(7)]
  //const currentAnecdote = anecdotes[randomI]

  //  const mostPopular = () => { 
  //  const copy = { ...points }
  //  copy[popular] += 1
  //  setPopular(anecdotes[points.indexOf(Math.max.apply(...points))])
  //  let indexOfPop = points.indexOf(Math.max.apply(...points));
  //  setPopular(anecdotes[indexOfPop])
 //  }

/*  const Winner = ({anecdotes, points}) => {
  const highestVoteCount = Math.max(...points)
  const winnerIndex = points.indexOf(highestVoteCount)
  const winner = anecdotes[winnerIndex]
  if (highestVoteCount === 0) {
    return (
      <p>No votes yet</p>
    )
  } */

/*   return (
    <div>
      <p>{winner}</p>
      <p>has {highestVoteCount} votes</p>
    </div>
  )
} */


  const ClickHandler = () => {
    let randomAnecdote = Math.floor(Math.random(selected) * anecdotes.length)
    setSelected(randomAnecdote);     
  }

  const VoteHandler = () => {
    //const newPoints = points; 
    //const copy = { ...points }
    //setVoted(copy, currentAnecdote = () => points.push(copy[currentAnecdote]) +=1)
    //copy[currentAnecdote] +=1;
    //if(randomI === copy[randomI]){
    const copy = { ...points }
    const bgst = Math.max(copy);
    copy[selected] += 1
    setPoints(copy)
    /* copy[popular] += 1
    setPopular(anecdotes[points.indexOf[bgst]]) */
    //setSelected(selected)
    //}
    //setResults({ ...results, [choice]: (results[choice] ?? 0) + 1 });
    console.log(copy)
    console.log(points)
    //console.log(testArray)
    console.log(bgst)

  }

  //console.log(getMaxVotes)
  console.log(points)

  return (
    <div>
      <h2>Anecdote of the day</h2>
      {anecdotes[selected]} has {points[selected]} votes
      <br/>
      <div>
      <button onClick={VoteHandler} >vote!</button>
      <button onClick={ClickHandler}>next anecdote</button>
      </div>
      <br/>
      <h2>Anecdote with most votes</h2>
     
       

    </div>
  )
}

export default App

______________________________________________

index.js

import ReactDOM from 'react-dom/client'
import App from './App'


ReactDOM.createRoot(document.getElementById('root')).render(<App />)
