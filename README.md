# java-code
/*
 * To change this license header, choose License Headers in Project Properties.
 * To change this template file, choose Tools | Templates
 * and open the template in the editor.
 */
package input;


import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.io.*;
import static java.lang.System.out;

import java.util.*;

import javax.swing.*;
/**
 *
 * @author Poonam
 */
 public class userinput
 {
     public static void main(String[] args)
     { Input n=new Input();
 }}
 class Input extends JFrame {

JFrame frame= new JFrame();
JTextArea tarea = new JTextArea(200, 100);
   String t=tarea.getText();
        JButton l=new JButton("ok");   
         JButton  readButton = new JButton("OPEN FILE");
       
        JFileChooser fc = new JFileChooser();
         public Input()
                 {                    
        
   
                
            

                               add(l);
                         add(readButton);
              
                         add(tarea);
                  
     
                       readButton.addActionListener(new ActionListener() {

                     public void actionPerformed(ActionEvent ev) {
                         int returnVal = fc.showOpenDialog(frame);
                         if (returnVal == JFileChooser.APPROVE_OPTION) {
                             File file = fc.getSelectedFile();
                            
                             try {
                                 BufferedReader input = new BufferedReader(new InputStreamReader(
                                         new FileInputStream(file)));
                                 tarea.read(input, "READING FILE");
                            
                               
                               
                             } catch (Exception e) {
                                 
          e.printStackTrace();
        }
      
                             }
                          else {
                             System.out.println("Operation is CANCELLED");
                         }              }
                 });
                         
                             
                  
                  setLayout(new FlowLayout()); // anonymous object creation
setVisible(true);
setSize(400,400);
setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

    }


    
}
