# Card
## components/UI/Card.js
```javascript
import classes from "./Card.module.css";

const Card = (props) => {
  return <div className={classes.card}>{props.children}</div>;
};

export default Card;
```
## components/UI/Card.module.css
```css
.card {
    margin: 3%;
    padding: 2rem;
    box-shadow: 0 2px 8px rgba(0, 0, 0, 0.25);
    border-radius: 14px;
    background-color: white;
    text-align: center;
}
```
