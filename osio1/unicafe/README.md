
App.js

import { useState } from 'react'

 const Statistics = (props) => {return (
  <div>
    <h2>Statistics</h2>
    <table>
      <tbody>      
      <tr>
        <td>good</td> 
        <td>{props.good}</td>
      </tr>
      <tr>
        <td>neutral </td> 
        <td>{props.neutral}</td>
      </tr>
      <tr>
        <td>bad </td>
        <td>{props.bad}</td>
      </tr>
      <tr>
        <td>all</td> 
        <td>{props.all}</td>
      </tr>
      <tr>
        <td>avarage </td>
        <td>{props.avg}</td> 
      </tr>
      <tr>
        <td>positive </td>
        <td>{props.pos} %</td>
      </tr>
    </tbody>
    </table>
    </div>
  
  )
 
}

const App = () => {
  // tallenna napit omaan tilaansa
  const [good, setGood] = useState(0)
  const [neutral, setNeutral] = useState(0)
  const [bad, setBad] = useState(0)
  const [all, setAll] = useState(0)
  const [avgsum, setAvgsum] = useState(0)
  const avg = avgsum/all;
  const pos = good/all * 100;

  const GoodClickHandler = () => {
    setAll(all +1); 
    setGood(good +1);
    setAvgsum(avgsum+1);
   /*  setAvg(avgsum/all);
    setPos(good/all * 100); */
     
  }

  const NeutralClickHandler = () => {
    setAll(all +1)
    setNeutral(neutral +1)
   /*  setAvg(avgsum/all)
    setPos(good/all * 100) */
  
 }

 const BadClickHandler = () => {
  setBad(bad +1)
  setAll(all +1)
  setAvgsum(avgsum -1)
 /*  setAvg(avgsum/all)
  setPos(good/all * 100) */

}

   //avg = avgsum/all;
/* const AvgHandler = (avgsum, all)=>{
   setAvg(avgsum/all)
} */

  console.log(avg)
  console.log(pos)

  return (
    <div>

      <h2>Give Feedback</h2>
      <button onClick={GoodClickHandler}>good</button>
      <button onClick={NeutralClickHandler}>neutral</button>
      <button onClick={BadClickHandler}>bad</button>
   
    <Statistics good = {good} neutral={neutral} bad={bad} all={all} avg={avg} pos={pos}/>  
    </div> 
  )
 
}
export default App;
________________________________________________________________________________________

index.js

import ReactDOM from 'react-dom/client'
import App from './App'


ReactDOM.createRoot(document.getElementById('root')).render(<App />)
