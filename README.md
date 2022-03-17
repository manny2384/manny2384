# 👋 Hi, my name is Emmanuel Gonzalez
## About
I earned my Bachelor's in Computer Science from California State University - East Bay in May 2021.
I focused more on data structures, web development, and databases while doing my curriculum. Since graduating, I've grown even more 
interests in Web Dev, Machine Learning, and AI.

## Projects
  ### 1
  #### This project is a challenge from FrontEndMentor. I attempt to recreate the webpage based on the figma design. I integrated flex box properties and media queries to produce the optimal layout based on user device. 
  - [live site](https://zealous-wright-cb2f9c.netlify.app/)
  - [repository](https://github.com/manny2384/FrontEndMentor/tree/main/gallery/src)
  - ![](https://github.com/manny2384/FrontEndMentor/blob/main/gallery/art-gallery-website/desktop.png)
  
  ### 2
  #### This project focused on API calls from client side. It served as a means of getting comfortable with JSON data and managing network calls.
  - [live site](https://weatherproj-7f551.web.app)
  - [repository](https://github.com/manny2384/weather)
    
  ### 3
  #### My planets project is composed of learning functional components in REACT and using a JSON data file to serve each component depending on the planet name( state )
  - [live site](https://manny2384.github.io/planets/)
  - [repository](https://github.com/manny2384/planets)
  - ![Planets Gif](https://github.com/manny2384/planets/blob/main/planets.gif)
  
  ### 4
  #### This project was 1 of the challenges I took from FrontEndMentor. The goal was the recreate the loopstudios landing page as close as possible by making judgements based off the design. The secondary goal was to make it a responsive design for both mobile and desktops.
  
    - [site](https://manny2384.github.io/LoopStudios/)
    - [repository](https://github.com/manny2384/LoopStudios/tree/master)
   
## Interests
### 🌱 As I said before, lately I've been interested in learning about Machine Learning and since I didn't get the chance to learn at while in school, I've been taking online courses to learn at my own pace. Currently I have a few projects I built apart from course excercise

#### This project implements multivariate regression. The goal of the project was to implement the algorithm from scratch by programming the functions for gradient descent, cost function, and vectorizing the computations to increase speed. 
  - ![Code on Kaggle](https://www.kaggle.com/code/manny2384/medical-cost-lr)
  - ![Medical Regression Gif](https://github.com/manny2384/Algorithms/blob/master/MedicalRegression.gif)
  
 #### This project was built after learning how games such as tic tac toe define a move via minimax decision making.
  - [AI Game](https://manny2384.github.io/manny2384games.github.io/)
  - [repository](https://github.com/manny2384/manny2384games.github.io)
  - minimax algorithm
  ```js
     // performs minimax decision making: recursive
    // @ params board = recursive board
    // @ player = current player: switches on each recursion
function minimax(board, player, depth){
        if(gameOver(board) || depth === 0){
            return [evaluateBoard(board), ''];
        }

        // performs oscillates player to perform best calcution of turn

        let best_move;
        if(player){
            var best_value = -1000;
            var symbol = 'X';
        } 
        else{
            var best_value = 1000;
            var symbol = 'O';
        }
        // get available moves list
        let availableMoves = moves_available(board);

        
        for(let i=0; i<availableMoves.length; i++){
            // new deep copy of board
            let new_board = JSON.parse(JSON.stringify(board));

            select_Square_minimax(new_board, availableMoves[i], symbol);
            // recurse with opposing player turn
            let hypotheticalVal = minimax(new_board, !player, depth-1)[0];
            // checks comparison on x-player
            if(player && hypotheticalVal > best_value){
                best_value = hypotheticalVal;
                best_move = availableMoves[i];
            }
            // checks comparison on o-player
            else if(!player && hypotheticalVal < best_value){
                best_value = hypotheticalVal;
                best_move = availableMoves[i];
            }
            
        }


        // return list of best move and value
        return [best_value,best_move];
    }
  ```
  ![Gif of tic tac toe](https://github.com/manny2384/manny2384games.github.io/blob/master/GIFS/tictactoe.gif)        [TicTacToe Algorithm](https://github.com/manny2384/manny2384games.github.io/blob/master/src/tic-tac-toe.js)
     
 #### Implementation of BFS to find solutions for the Cannibal and Missionary problem
 -  [Complete Code](https://github.com/manny2384/Algorithms/blob/master/search/bfs.cpp)
 -  BFS Algorithm
 ```c++
 /*
    @params = node to initial state
    returns node pointing to solution
        or NULL if no solution found
*/
Node*BFS(Node*a){

    if(goal_test(a->state)){
        return a;
    }

    std::deque<Node*> frontier, explored;
    frontier.push_back(a);

    while(true){
        if (frontier.size() == 0){
            return NULL;
        }

        Node *p = frontier.front();
        explored.push_back(p);
        frontier.pop_front();

        for (std::string act : actions){
            Node* child = new Node();
            child->action = act;
            child->parent = p;
            child->boat = child->parent->boat == false ? true : false;
            child->state = do_action(child->parent->state, act, p->boat);

            // action was successful
            if(child->state != ""){
                
                if(!visited(child->state, child->boat, frontier) && !visited(child->state, child->boat, explored)){
       
                    if(goal_test(child->state)){
                        return child;
                    }
                    frontier.push_back(child);
                }
          
            }
            else delete child;
            
        }

    }

    // no solution was found
    return NULL;
}
 ```

- 📫 How to reach me 
Email: gonzalezeh97@gmail.com

<!---
manny2384/manny2384 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
