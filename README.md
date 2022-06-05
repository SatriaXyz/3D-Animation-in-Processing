int mula = 0;

int move = 4;

boolean rotasiX = false;

boolean rotasiY = false;

boolean rotasiZ = false;


void setup(){

  size(1000,1000,P3D);
  
}

void draw(){

  background(0);
  
  lights();
  
  translate(500, 500);
  
  stroke(255,255,0);
  
    line(0,-500,0,500);
    
    line(500,0,-500,0);
    
      stroke(255,0,0);
    
  pushMatrix();
  
    if(rotasiX){
    
      // Roll
      
      rotateX(radians(mula));
      
    }
    
    if(rotasiY){
    
      // Pitch
      
      rotateY(radians(mula));
      
    }
    
    if(rotasiZ){
    
      // Yaw
      
      rotateZ(radians(mula));
      
    }
    
    mula += move;
 
    if (mula < 0){
    
      move = -move;
      
      mula += move;
      
    }
    
    box(160,100,50);
    
  popMatrix();

}


void keyPressed(){

  if(key == 'x'){
  
    rotasiX = true;
    
    
  }
  
  if(key == 'y'){
  
    rotasiY = true;
    
  }
  
  if(key == 'z'){
  
    rotasiZ = true;
    
  }
  
}

void keyReleased(){

  if(key == 'x'){
  
    rotasiX = false;
    
  }
  
  if(key == 'y'){
  
    rotasiY = false;
    
  }
  
  if(key == 'z'){
  
    rotasiZ = false;
    
  }
  
}
