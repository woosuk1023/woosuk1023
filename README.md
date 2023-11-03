duck[] aa;
woosuk[] bb;
void setup() {
  size(2000, 1200);
  // 4 objects
  aa= new duck[20];
  bb = new woosuk[20];
  for(int i = 0; i<17; i++) {
  aa[i] = new duck(50*i, 50*i, random(100, 500)/100);
  bb[i] = new woosuk(width - 50*i, height - 50*i, random(100, 500)/100);
}
  aa[17] = new duck(100.,200.,2.5, random(300)/100, random(300)/100);
  aa[18] = new duck(200.,100.,3.1, random(300)/100, random(300)/100);
  aa[19] = new duck(300.,400.,5.2, random(300)/100, random(300)/100);
  
  bb[17] = new woosuk(width - 100.,height -200.,2.5, random(300)/100, random(300)/100);
  bb[18] = new woosuk(width - 200.,height -100.,3.1, random(300)/100, random(300)/100);
  bb[19] = new woosuk(width - 300.,height -400.,5.2, random(300)/100, random(300)/100);
}
void draw(){
  background(0, 255, 255);  
  // call member function
  
  for (int i=0; i<20; i++){
    for (int a = 0 ; a < 19 - i; a++){
    aa[i].collision(aa[19-a]);
    }
    for (int a = 0 ; a < 19 - i; a++){
    bb[i].collision(bb[19-a]);
    }
    for (int a = 0 ; a < 20; a++){
    bb[i].collision(aa[a]);
    } 
    aa[i].move();
    aa[i].display();
    bb[i].move();
    bb[i].display();
  }
}
