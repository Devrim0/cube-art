# cube-art


package tektopsektrime;
import java.applet.Applet;
import java.awt.Color;
import java.awt.Graphics;
import java.util.logging.Level;


import javax.swing.JApplet;

public class TOPSEKTİRİME extends JApplet implements Runnable{
int karex=0,karey=0,r=40;
Thread ciz;
    
    public void run() {
       this.resize(500,300);
       while(this.getWidth()>karex+r){//birincisi
      karex+=10;
       repaint();
      try {
        Thread.sleep(50);
       } catch (InterruptedException ex) {
       }
       }
         while(this.getHeight()>karey+r){//ikincisi
               karey+=10;
               karey*=+1;
          
          try { repaint();
               Thread.sleep(30);
           } catch (InterruptedException ex) {
               Logger.getLogger(TOPSEKTİRİME.class.getName()).log(Level.SEVERE, null, ex);
           }
          if(this.getHeight()<=karey+r){karey*=-1;
          }
        
          repaint();
    }}
    public void paint(Graphics g){
        g.setColor(Color.red);
    g.clearRect(0, 0,this.getSize().width, this.getSize().height);
    g.fillRect(karex,karey,r,r);
    }
    public void start(){
    if(ciz==null){
    ciz=new Thread(this);
    ciz.start();}
    
    }
    public void stop(){
        if(ciz!=null){
    ciz.stop();
    
        }}
    
}  




