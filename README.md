# proyecto
package Proyecto;

import java.awt.EventQueue;

public class PInterface {

	private String Name;
	private String Docu;
    static String summery;
	
	private JFrame frame;
	private JPanel panelPrincipal;
	private JPanel panelRegistro;
	private JPanel panelDocs;
	private JTextField textNombre;
	private JTextField textDoc;
	private JTextField textUni;
		

	
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					PInterface window = new PInterface();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}


	public PInterface() {
		initialize();
	}

	
	private void initialize() {
		frame = new JFrame();
		final JPanel panelPrincipal = new JPanel();
		final JPanel panelRegistro = new JPanel();
		final JPanel panelBuscar = new JPanel();
		JLabel lblNewLabel = new JLabel("Universidad el Bosque");
		JButton btnNewButton = new JButton("Registro");
		
		frame.setBounds(100, 100, 470, 450);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.getContentPane().setLayout(new CardLayout(0, 0));
			
		panelPrincipal.setBackground(new Color(0, 204, 0));
		frame.getContentPane().add(panelPrincipal, "name_28760679523292");
		panelPrincipal.setLayout(null);
		panelPrincipal.setVisible(true);
		
		panelRegistro.setBackground(new Color(50, 205, 50));
		frame.getContentPane().add(panelRegistro, "name_28762097496843");
		panelRegistro.setLayout(null);
		panelRegistro.setVisible(false);
				
		panelBuscar.setBackground(new Color(0, 204, 0));
		frame.getContentPane().add(panelBuscar, "name_35942583994442");
		panelBuscar.setLayout(null);
		panelBuscar.setVisible(false);
		
		lblNewLabel.setFont(new Font("Tahoma", Font.PLAIN, 17));
		lblNewLabel.setBounds(137, 21, 185, 60);
		panelPrincipal.add(lblNewLabel);
		
		btnNewButton.setFont(new Font("Tahoma", Font.PLAIN, 12));
		btnNewButton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				panelRegistro.setVisible(true);
				panelPrincipal.setVisible(false);
			}
		});
		btnNewButton.setBounds(180, 160, 108, 47);
		panelPrincipal.add(btnNewButton);
		
		JButton btnNewButton_1 = new JButton("Ver registros");
		btnNewButton_1.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				panelPrincipal.setVisible(false);
				panelBuscar.setVisible(true);
			}
		});
		btnNewButton_1.setBounds(171, 224, 128, 23);
		panelPrincipal.add(btnNewButton_1);
		
		
		final JButton btnTerminar = new JButton("Terminar");
		btnTerminar.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				
				panelPrincipal.setVisible(true);
				panelRegistro.setVisible(false);
			}
		});
		btnTerminar.setBounds(158, 377, 89, 23);
		panelRegistro.add(btnTerminar);
		
		JLabel lblUniversidadElBosque = new JLabel("Universidad el Bosque");
		lblUniversidadElBosque.setBounds(170, 11, 134, 23);
		panelRegistro.add(lblUniversidadElBosque);
		
		textNombre = new JTextField();
		textNombre.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				
	if(e.getSource()==btnTerminar){
					
					Name = ("");
					Name = textNombre.getText().trim();
					Docu = ("");
					Docu = textDoc.getText().trim();
					summery = ("Nombre "+ Name) + ("Documento "+Docu);
				}
				
				
			}
		});
		textNombre.addKeyListener(new KeyAdapter() {
			
			@Override
			public void keyTyped(KeyEvent e) {
				char c=e.getKeyChar();
				if(Character.isDigit(c)){
				e.consume();
				}
			}
		});
		textNombre.setBounds(158, 66, 120, 20);
		panelRegistro.add(textNombre);
		textNombre.setColumns(10);
		
		JLabel lblNombreCompleto = new JLabel("Nombre completo :");
		lblNombreCompleto.setBounds(20, 69, 128, 14);
		panelRegistro.add(lblNombreCompleto);
		
		JComboBox comboBox = new JComboBox();
		comboBox.setModel(new DefaultComboBoxModel(new String[] {"Tipo de documento","Cedula de ciudadania", "Tarjeta de identidad"}));
		comboBox.setBounds(20, 98, 133, 20);
		panelRegistro.add(comboBox);
		
		JLabel lblNmeroDeDocumento = new JLabel("No. de documento:");
		lblNmeroDeDocumento.setBounds(20, 125, 106, 14);
		panelRegistro.add(lblNmeroDeDocumento);
		
		textDoc = new JTextField();
		textDoc.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				
	if(e.getSource()==btnTerminar){
					
					
					summery = ("Nombre "+ Name) + ("Documento "+Docu);
				}
				
			}
		});
		textDoc.addKeyListener(new KeyAdapter() {
			@Override
			public void keyTyped(KeyEvent e) {
				char c=e.getKeyChar();
				if(Character.isAlphabetic(c)){
				e.consume();
				}
			}
		});
		textDoc.setBounds(170, 119, 106, 20);
		panelRegistro.add(textDoc);
		textDoc.setColumns(10);
		
		JLabel lblDocumentosRequeridos = new JLabel("Documentos Requeridos:");
		lblDocumentosRequeridos.setFont(new Font("Tahoma", Font.BOLD, 12));
		lblDocumentosRequeridos.setBounds(134, 150, 154, 14);
		panelRegistro.add(lblDocumentosRequeridos);
		
		JComboBox comboBox_1 = new JComboBox();
		comboBox_1.setModel(new DefaultComboBoxModel(new String[] {"Horario","Diurno", "Nocturno"}));
		comboBox_1.setBounds(255, 337, 104, 20);
		panelRegistro.add(comboBox_1);
		
		JLabel lblTransferencia = new JLabel("Transferencia:");
		lblTransferencia.setBounds(20, 312, 106, 14);
		panelRegistro.add(lblTransferencia);
		
		JLabel lblUniversidad = new JLabel("Universidad:");
		lblUniversidad.setBounds(210, 312, 78, 14);
		panelRegistro.add(lblUniversidad);
		
		textUni = new JTextField();
		textUni.addKeyListener(new KeyAdapter() {
			@Override
			public void keyTyped(KeyEvent e) {
				char c=e.getKeyChar();
				if(Character.isDigit(c)){
				e.consume();
			}
			}
		});
		textUni.setText("");
		textUni.setBounds(285, 309, 143, 20);
		panelRegistro.add(textUni);
		textUni.setColumns(10);
		
		JComboBox comboBox_3 = new JComboBox();
		comboBox_3.setModel(new DefaultComboBoxModel(new String[] {"Programa:","Ingenier\u00EDa de Sistemas", "Ingenier\u00EDa Electr\u00F3nica", "Bioingeneria", "Ingenieria Ambiental", "Ingenieria Industrial"}));
		comboBox_3.setBounds(19, 337, 134, 20);
		panelRegistro.add(comboBox_3);
		
		JCheckBox chckbxNewCheckBox = new JCheckBox("Fotocopia D.I");
		chckbxNewCheckBox.setBounds(47, 183, 148, 23);
		panelRegistro.add(chckbxNewCheckBox);
		
		JCheckBox chckbxFotoX = new JCheckBox("Foto 3 x 4");
		chckbxFotoX.setBounds(226, 183, 148, 23);
		panelRegistro.add(chckbxFotoX);
		
		JCheckBox chckbxExamenSaber = new JCheckBox("Examen Saber 11");
		chckbxExamenSaber.setBounds(47, 220, 148, 23);
		panelRegistro.add(chckbxExamenSaber);
		
		JCheckBox chckbxFotocopiaDiploma = new JCheckBox("Fotocopia Diploma");
		chckbxFotocopiaDiploma.setBounds(226, 220, 148, 23);
		panelRegistro.add(chckbxFotocopiaDiploma);
		
		JCheckBox chckbxFotocopiaEps = new JCheckBox("Fotocopia EPS");
		chckbxFotocopiaEps.setBounds(140, 251, 148, 23);
		panelRegistro.add(chckbxFotocopiaEps);
	
	    ButtonGroup grupo = new ButtonGroup();
	    
		JRadioButton a = new JRadioButton("Si");
		a.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
			textUni.setEditable(true);
			}
		});
		a.setBounds(108, 308, 40, 23);
		panelRegistro.add(a);
		
		
		JRadioButton b = new JRadioButton("No");
		
		b.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				textUni.setEditable(false);
			
			}
				
		}
		
		);
		grupo.add(a);
		grupo.add(b);
		
		b.setBounds(155, 308, 40, 23);
		panelRegistro.add(b);
		
		JLabel lblRegistro = new JLabel("Registro");
		lblRegistro.setBounds(182, 41, 65, 14);
		panelRegistro.add(lblRegistro);
		lblRegistro.setFont(new Font("Tahoma", Font.BOLD, 12));
		
		
		JLabel lblNewLabel_2 = new JLabel("Informaci\u00F3n");
		lblNewLabel_2.setFont(new Font("Tahoma", Font.PLAIN, 15));
		lblNewLabel_2.setHorizontalAlignment(SwingConstants.TRAILING);
		lblNewLabel_2.setBounds(124, 26, 150, 14);
		panelBuscar.add(lblNewLabel_2);
		
		JButton btnRegresar = new JButton("Regresar");
		btnRegresar.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {
				
				panelPrincipal.setVisible(true);
				panelBuscar.setVisible(false);
			}
		});
		btnRegresar.setBounds(171, 340, 89, 23);
		panelBuscar.add(btnRegresar);
		
		JLabel lblNewLabel_1 = new JLabel("Buscar por cedula:");
		lblNewLabel_1.setBounds(35, 75, 144, 23);
		panelBuscar.add(lblNewLabel_1);
		
		JLabel lblBuscarPorNombre = new JLabel("Buscar por nombre:");
		lblBuscarPorNombre.setBounds(35, 109, 144, 14);
		panelBuscar.add(lblBuscarPorNombre);
		
		JLabel lblBuscarPorDocumentacin = new JLabel("Buscar por Documentaci\u00F3n:");
		lblBuscarPorDocumentacin.setBounds(35, 134, 198, 14);
		panelBuscar.add(lblBuscarPorDocumentacin);
		
		
	}
}
