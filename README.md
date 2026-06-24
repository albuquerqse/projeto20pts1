package projeto
import javax.swing.*;
import java.awt.Font;
import java.util.Random;
public class trabalho {

	public static void main(String[] args) {
		String [] fab = {"Entrada", "Esteira de Soldagem", "Inspeção de Qualidade", "Pintura Automatizada", "Embalagem", "Estoque final"};
		int pAt = 0;
		
		Random ger = new Random();
		
		JOptionPane.showMessageDialog(null,  "Estagio inicial","Fabrica",JOptionPane.INFORMATION_MESSAGE);
		
		while(pAt < fab.length -1) {
			int escol = JOptionPane.showConfirmDialog(null, "Seu produto esta no setor " + pAt + " (" + fab[pAt] + "). Deseja rodar o dado?", "Sua vez", JOptionPane.YES_NO_OPTION);
			
			if (escol == JOptionPane.YES_OPTION) {
				int dado = ger.nextInt(2) +1;
				pAt +=dado;
				
				if(pAt>=fab.length) {
					pAt=fab.length - 1;
					
				}
				
				JOptionPane.showMessageDialog(null,"o dado caiu em: "+dado+"\n você avançou para a casa "+pAt," Movimento",JOptionPane.WARNING_MESSAGE);
				
				switch (fab[pAt]) {
				case "Esteira de Soldagem":
					JOptionPane.showMessageDialog(null,"O processo foi concluido com sucesso!","Setor de soldagem",JOptionPane.INFORMATION_MESSAGE);
					break;
				case "Inspeção de Qualidade":
					int teste = ger.nextInt(2);
					JOptionPane.showMessageDialog(null,"Ouve uma parada de inspeção","Inspeção",JOptionPane.INFORMATION_MESSAGE);
					if (teste==1) {
						JOptionPane.showMessageDialog(null,"Esta tudo ok","Inspeção",JOptionPane.INFORMATION_MESSAGE);
					}else {
						JOptionPane.showMessageDialog(null,"Contem erros","Inspeção",JOptionPane.INFORMATION_MESSAGE);
						pAt--;
					}
					break;
				case "Pintura Automatizada":
					JOptionPane.showMessageDialog(null,"A tinta secou sem problemas","Pintura",JOptionPane.INFORMATION_MESSAGE);
					break;
				case "Embalagem":
					JOptionPane.showMessageDialog(null,"Emabalado com sucesso","Embalagem",JOptionPane.INFORMATION_MESSAGE);
					break;
				case "Estoque final":
					JOptionPane.showMessageDialog(null,"o lote foi fechado e esta pronto para o envio","Estoque",JOptionPane.INFORMATION_MESSAGE);
					break;
				}
					
			}else {
				JOptionPane.showMessageDialog(null,"Montagem parada ate segunda tentativa");

			}
			
		}
		JOptionPane.showMessageDialog(null,"Fim da montagem\n Parabens pelo trabalho");
	}

}

