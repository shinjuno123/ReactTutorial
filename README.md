### The Summary for React.js 

I focused on Data's move and how rendering begins and ends in React.js

so I started to draw the rendering process in my head 
when this web application is loaded, It will call 'Game' class first 

so here's the code to call 'Game'

<pre>
<code>
ReactDOM.render(
    <Game />,
    document.getElementById('root')
);
</code>
</pre>

 

This Game class definitely will call 'Board' class




    class Game extends React.Component {
        //there are other codes
        return (
    
            <div className="game">
                <div className="game-board">
                    <Board  // board class
                        squares = {current.squares}
                        onClick={(i)=>this.handleClick(i)}
                        />
                </div>
                <div className="game-info">
                    <div>{status}</div>
                    <ol>{moves}</ol>
                </div>
            </div>
            
        );
  
    };


  
but besides that it will call 'status' variable and 'moves' variable too
first we will see 'status' variable and the related functions and variables

this is 'status' variable

    let status;
    if(winner){
        status = 'Winner: '+ winner;
    }else{
        status = 'Next Player: '+(this.state.xIsNext ? 'X':'O');
    }
if you just look into this code,you could know If there is winner's value, it will call 'if' If winner is none or false it will call 'else' 


so You also have to see 'winner' variable too 

    const winner = calculateWinnter(current.squares);

at this part you will think this
'hmm.. winner variable definitely will get some value from winner I guess'


this will call 'calculateWinner' function too
so we will see 'calculateWinner' function

    function calculateWinnter(squares){
        const lines = [
            [0,1,2],
            [3,4,5],
            [6,7,8],
            [0,3,6],
            [1,4,7],
            [2,5,8],
            [0,4,8],
            [2,4,6],
        ];

        for(let i=0;i<lines.length;i++){
            const [a,b,c] = lines[i];
            if(squares[a] && squares[a] === squares[b] && squares[a] === squares[c]){
                return squares[a];
            }
        }

        return null;
    }
    

so 'lines' is the cases of winner. In 'for' If squares[a] is same with squares[a] and squares[b] and
squares[c], then you will return 'squares[a]' or you will return null.

so the 'winner' variable will get the value from function 'calculateWinner'
if 'winner' variable's value is not null then as I told you 

    let status;
    if(winner){
        status = 'Winner: '+ winner;
    }else{
        status = 'Next Player: '+(this.state.xIsNext ? 'X':'O');
    }
this code will save the winner in 'status' variable and this will show you the winner 

        return (
            <div className="game">
                <div className="game-board">
                    <Board 
                        squares = {current.squares}
                        onClick={(i)=>this.handleClick(i)}
                    />
                </div>
                <div className="game-info">
                    <div>{status}</div> // you will see who is the winner here
                    <ol>{moves}</ol>
                </div>
            </div>
        );

so there is also 'else' part in this code

    if(winner){
        status = 'Winner: '+ winner;
    }else{
        status = 'Next Player: '+(this.state.xIsNext ? 'X':'O');
    }
     
then you can see 'this.state.xIsNext ? 'X':'O'' this line then we have to go to 'state' of this 'Game' class

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
    
state is in constructor.React said that constructor is necessary to use 'state' so anyway
There is 'xIsNext: true,' this code so if you compare this 2 lines


        status = 'Next Player: '+(this.state.xIsNext ? 'X':'O');
        xIsNext: true,

Then you will realize that 'true' would be 'X' 'false' would be 'O' and you will save the value in the variable 'status' and it will show you whose turn is when winner is not still decided.


then Let's get back to first code 
Now we will follow the flows of variable 'moves'

    class Game extends React.Component {
        //there are other codes
        return (
    
            <div className="game">
                <div className="game-board">
                    <Board  // board class
                        squares = {current.squares}
                        onClick={(i)=>this.handleClick(i)}
                        />
                </div>
                <div className="game-info">
                    <div>{status}</div>
                    <ol>{moves}</ol>
                </div>
            </div>
            
        );
  
    };











  
