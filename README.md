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

2. classes or functions work like a tag in jsx

        <Board 
            squares = {current.squares}
            onClick={(i)=>this.handleClick(i)}
        /> 
  
3. 'render' function is necessary

        render() {
     
            return (
                <div>
                    <div className="board-row">
                        {this.renderSquare(0)}
                        {this.renderSquare(1)}
                        {this.renderSquare(2)}
                    </div>
                    <div className="board-row">
                        {this.renderSquare(3)}
                        {this.renderSquare(4)}
                        {this.renderSquare(5)}
                    </div>
                    <div className="board-row">
                        {this.renderSquare(6)}
                        {this.renderSquare(7)}
                        {this.renderSquare(8)}
                    </div>
                </div>
            );
        }

4. If you want to make or use some variables, then Make 'constructor' and write 'state' variable in json form

        constructor(props){
            super(props);
            this.state={
                history:[{
                    squares: Array(9).fill(null),
                }],
                stepNumber: 0,
                xIsNext: true,
            }
        }
    
5. 'props' means the property of the 'class' or 'function' that you wrote like a tag. so you can name the properties name as you want

        //first lines
        <Square 
            value={this.props.squares[i]}
            onClick={()=>this.props.onClick(i)}
         />
        //second lines
        <Board 
            squares = {current.squares}
            onClick={(i)=>this.handleClick(i)}
         />
6. You don't have to use 'jsx' but using 'jsx' is more efficient and convenient. so Use it

7. This is not about 'React.js' but It is good not to change the orginal data when you want to leave the records of the past of your web app
<pr>
<code>    
        const history = this.state.history.slice(0,this.state.stepNumber+1);
</code>    
</pr>


What I felt from this

Redux Would be a good combination definitely because usually In a big project,the Project needs big and organized space in your flash memory before you insert your data to Database so I'll have to use
React with Redux together
