# Puyo_Puyo
Amusez vous bien Kappa

const int NBCOLORS = 5, HEIGHT = ?, WIDTH = ?, FALLSPEED = ?, SIZEPUYO = ?, WIDTHMAT = ?, HEIGHTMAT = ?, WAITINGPOSX = ?, WAITINGPOSY = ?;

struct Pos {
	int x ;
	int y ;
}

struct Block {
	bool exist;
	char color;
	int groupID;
}

struct BlockFall {
	entier orient ;
	char color1 ;
	char color2 ; 
	Pos posMat ; 
	int speed ; 
}

struct Player {
	BlockFall bf1;
	BlockFall bf2 ;
	Block blocks[][] //pas sure de ca ;
	int score ;
}

struct Game {
	Player p1;
	Player p2; 
}

initBlockFall

switchColor

random0toNb

randBlockFall

startTour

blockTest

doGravityOnAll

continueFall

blockDown

AttribuerGroupe - Anton

checkAllChains - Anton

bool blockAtStart (int[][] blocks) {
	return (blockTest(blocks,0,(WIDTHMAT/2 -1)) || blockTest(blocks,0,WIDTHMAT/2));
}

int countNbBlocksEqualID (block[][] mat, int ID) {
	int nb = 0; 
	for (int i = 0 ; i < WIDTHMAT ; i++) {
		for (int j = 0 ; j < HEIGHTMAT ; j++) {
			if (mat[i][j].groupID == ID) {
				nb ++ ;
			}
		}
	}
	return nb;
}

void setMalusOnPlayer (Player p1, int reps) {
	int nb ; 
	for (int i = 0 ; i < reps ; i++) {
		nb = random0toNb(WIDTHMAT);
		if (p1.blocks[0][nb].exist == false) {
			p1.blocks[i][0].color = w ;
			p1.blocks[i][0].exist = true ; 
			doGravityOnAll(p1.blocks);		
		}
	}
}

void resetBlocksForID (Block[][] block, int ID) {
	for (int i = 0 ; i < WIDTHMAT ; i++) {
		for (int j = 0 ; j < HEIGHTMAT ; j++) {
			if (block[i][j].blockID == ID && block[i][j].color !w) {
				block[i][j].exist = false ;
				block[i][j].color = v ; 
				if (block[i][j+1].color == w) {
					block[i][j+1].exist = false ; 
					block[i][j+1].color = v ; 
				}
				if (block[i][j-1].color == w) {
					block[i][j-1].exist = false ; 
					block[i][j-1].color = v ; 
				}
				if (block[i-1][j].color == w) {
					block[i-1][j].exist = false ; 
					block[i-1][j].color = v ; 
				}
				if (block[i+1][j].color == w) {
					block[i+1][j].exist = false ; 
					block[i+1][j].color = v ; 
				}
			}
		}
	}
}

int destroyBlock (block[][] mat) {
	int nbrChain = 0 ; 
	for (int k = 1 ; k < WIDTHMAT*HEIGHTMAT ; k++ ) {
		if (countNbBlocksEqualId(mat, k)>3) {
			resetBlocksForId(mat, k) ; 
			nbrChain ++ ; 
		}
	} 
	for (int i = 0 ; i < WIDTHMAT ; i++) {
		for (int j = 0 ; j < HEIGHTMAT ; j++) {
			mat[i][j].blockID = 0 ; 
		}
	}
	return nbrChain ; 
}

int main {
	bool doStartTour, gameOver ; 
	int penaltyReps1, penaltyReps2; 


	return 0 ;
}
