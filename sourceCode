void setup()
{
  size(600, 600);
}

float speeds = 0;
float speedm = 0;
float speedh = 0;

void draw()
{
  int h = hour()%12;
  int m = minute(); 
  int s = second();
  float hr = map(h,0,12,0,12);
  float mr = map(m,0,59,0,8);
  float sr = map(s,0,59,0,8);
  speeds = (speeds + sr) % 360;
   println(speeds);
  speedm = (speedm + mr) % 360;
  println(speedm);
  speedh = (speedh + hr) % 360;
  println(speedh);
  circleDraw(width/2, height/2, width);
  
}


void circleDraw(float xpoint, float ypoint, float diam)
{
  int realh = hour();
  
  float sdiam = diam / 4;
  float mdiam = diam * 1 / 6;
  float hdiam = diam / 10;
  
  circle(xpoint, ypoint, diam);
   
  if (hdiam > 1)
  {
    circleDraw(xpoint + ((diam / 2) - (sdiam / 2))*sin(radians(speeds)) ,ypoint + ((diam / 2) - (sdiam / 2)) * cos(radians(speeds)), sdiam); // second
    circleDraw(xpoint + ((diam / 2) - sdiam - (mdiam / 2))*sin(radians(speedm)) ,ypoint + ((diam / 2) - sdiam - (mdiam / 2)) * cos(radians(speedm)), mdiam); //minute
    if(realh < 13)
    {
      circleDraw(xpoint + ((diam / 2) - sdiam - mdiam - (hdiam/2))*sin(radians(speedh)) ,ypoint + ((diam / 2) - sdiam - mdiam - (hdiam/2)) * cos(radians(speedh)), hdiam); // hour
    }
    else if (realh > 12)
    {
      circleDraw(xpoint -( ((diam / 2) - sdiam - mdiam - (hdiam/2))*sin(radians(speedh))) ,ypoint +( ((diam / 2) - sdiam - mdiam - (hdiam/2)) * cos(radians(speedh))), hdiam); // hour
    }
  }
}
