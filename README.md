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


***
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
***

  
but besides that it will call 'status' variable and 'moves' variable too
first we will see 'status' variable and the related functions and variables

this is 'status' variable
let status;
if(winner){
       status = 'Winner: '+ winner;
}else{
       status = 'Next Player: '+(this.state.xIsNext ? 'X':'O');
}
if you just look into this code,you could know If winner is true or there is winner's value, it will call 'if' If winner is none or false it will call 'else' 


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
squares[c], then you will return 'squares[a]' or you will return null 











  
  
  
