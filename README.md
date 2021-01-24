### The Summary for React.js 

so I'll organize functions what I learned when I completed the tutorial of React.js


1. this is necessary anyway

<pr>
<code>    
    class Game extends React.Component{
    //code
    }
</code>    
</pr>

1. classes or functions work like a tag in jsx
<pr>
<code
    <Board 
        squares = {current.squares}
        onClick={(i)=>this.handleClick(i)}
    />
</code>    
</pr>    
2. 'render' function is necessary

3. If you want to make or use some variables, then Make 'constructor' and write 'state' variable in json form

4. 'props' means the property of the 'class' or 'function' that you wrote like a tag.so you can name the properties name as you want


5. You don't have to use 'jsx' but using 'jsx' is more efficient and convenient. so Use it

6. This is not about 'React.js' but It is good not to change the orginal data when you want to leave the records of the past of your web app
<pr>
<code>    
    const history = this.state.history.slice(0,this.state.stepNumber+1);
</code>    
</pr>


  
