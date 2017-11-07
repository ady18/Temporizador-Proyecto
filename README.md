# Temporizador-Proyecto
package poo;

import javax.swing.*;
import java.awt.event.*;
import java.util.*;
import javax.swing.Timer;
import java.awt.Toolkit;

public class PruebaTemporizador3 {

	public static void main(String[] args) {
		
		Reloj1 mireloj = new Reloj1();
		
		mireloj.enMarcha1(3000, true);
		
		JOptionPane.showMessageDialog(null, "Pulsa Aceptar para terminar");
		System.exit(0); //Para cuándo el usuario presione el botón de aceptar se detenga el programa

	}

}

class Reloj1{
	
	//Método que no devuelve ningún parámetro
	public void enMarcha1(int intervalo, final boolean sonido){
		
		//Clase Interna Local
		class DameLaHora2 implements ActionListener{
			
			public void actionPerformed(ActionEvent evento){
				
				Date ahora = new Date();
				
				System.out.println("Te pongo la hora a cada 3 seg: " + ahora);
				
				if(sonido){ //Es lo mismo que if(sonido==true)
					
					Toolkit.getDefaultToolkit().beep();
				}
							
			}
		}
		
		ActionListener oyente = new DameLaHora2();
		
		Timer mitemporizador = new Timer(intervalo, oyente);
		
		mitemporizador.start();
		
	}

}
