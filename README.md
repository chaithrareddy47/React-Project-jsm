# Rect projct from JSM mastery crash course 
# topics learnt and practised
 - logged in to tarck the 
import { useEffect, useState } from "react"

const Card = ({ name }) => {
  const [likes, setLikes] = useState(null)
  const [message, setMessage] = useState("")
  function handleLikes() {
    setLikes((prev) => prev === true ? null : true)
  }
  function handleDisLike() {
    setLikes((prev) => prev === false ? null : false)
  }
  useEffect(() => {
    if (likes === true) {
      setMessage("You liked")
    } else if (likes === false) {
      setMessage("u disliked")
    } else {
      setMessage("no reaction")
    }
    
},[likes])


  return (
    <div className="card">
      <p>{name}</p>
      <button onClick={handleLikes}
        className={
        likes === true ? "likes active" : "like"
      }
      >Like</button>
      <button onClick={handleDisLike}
        className={
          likes === false ? "dislike active" : "dislike"}
      >Dislike</button>
      <p>status :{ message}</p>
    </div>
  )
}

const App = () => {
  return (
    <div>
      <Card name="Avatar" />
      <Card name="Star Kings" />
      <Card name="Lion kings" />
    </div>
  )
}

export default App
