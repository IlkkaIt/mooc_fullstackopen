App.js

const App = () => {
  const course = {
    name: 'Half Stack application development',
    parts: [
      {
        name: 'Fundamentals of React',
        exercises: 10
      },
      {
        name: 'Using props to pass data',
        exercises: 7
      },
      {
        name: 'State of a component',
        exercises: 14
      }
    ]
  }
 

  return (
    <div>
      <Header course={course.name}/>
      <Content part1={course.parts[0].name} part2={course.parts[1].name} part3={course.parts[2].name} 
       exercises1={course.parts[0].exercises} exercises2={course.parts[1].exercises} exercises3={course.parts[2].exercises}/>
      <Total exercises1={course.parts[0].exercises} exercises2={course.parts[1].exercises} exercises3={course.parts[2].exercises} />
    </div>
  )
}

const Header = (props) => {
  return (
    <h1>{props.course}</h1>
  )

}

/* return (
  <div>
    <Part .../>
    <Part .../>
    <Part .../>
  </div>
) */

const Content = (props) => {
  return (
    <div>
      <Part1 part1={props.part1} exercises1={props.exercises1}/>
      <Part2 part2={props.part2} exercises2={props.exercises2}/>
      <Part3 part3={props.part3} exercises3={props.exercises3} />
   
    </div>

  )

}

const Part1 = (props) => {
  return (
    <div>
      <p> {props.part1}  {props.exercises1}</p>
    </div>
  )
}

const Part2 = (props) => {
  return (
    <div>
      <p>{props.part2} {props.exercises2}</p>
    </div>
  )
}

const Part3 = (props) => {
  return (
    <div>
      <p>{props.part3} {props.exercises3}</p>
    </div>
  )
}

const Total = (props) => {
  return (
    <div>
      <p>Number of exercises {props.exercises1} + {props.exercises2} + {props.exercises3}</p>
    </div>
  )
}


export default App

/* Refaktoroi sovelluksen koodi siten, että se koostuu kolmesta uudesta komponentista: 
Header, Content ja Total. Kaikki data pidetään edelleen komponentissa App, 
joka välittää tarpeelliset tiedot kullekin komponentille props:ien avulla. 
Header huolehtii kurssin nimen renderöimisestä, 
Content osista ja niiden tehtävämääristä ja Total tehtävien yhteismäärästä. */
________________________________________________________________________________________________________
index.js

import ReactDOM from "react-dom"
import App from "./App"

ReactDOM.render(<App />, document.getElementById("root"))
