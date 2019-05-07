import javax.swing.plaf.synth.SynthTextAreaUI;
import java.io.DataOutputStream;
import java.io.IOException;
import java.io.ObjectInputStream;
import java.io.ObjectOutputStream;
import java.net.InetAddress;
import java.net.Socket;
import java.util.Scanner;
public class Client {

 //   private static int LP = 5;
    private static int InitPort = 6789;
//	private static int IsWin = 0;
//  private static int IsLose = 0;
//	private static int MissCount = 0;
    private static String HOST = "127.0.0.1";
    private static Socket socket = null;
//    private static String SecretWord = "";
//    private static String Miss = "";
	private static ObjectOutputStream SocketOutput = null;
    private static ObjectInputStream SocketInput = null;
	

  
    public static void main( String[] args ) {
        Scanner keyboard;
		
        System.out.println("Connect to server " + HOST + ":" + InitPort);
        try {
          
            socket = new Socket(HOST, InitPort);
     
            SocketOutput = new ObjectOutputStream(socket.getOutputStream());
            SocketOutput.writeObject("Start");

        
            SocketInput = new ObjectInputStream(socket.getInputStream());
            String newPort = (String) SocketInput.readObject();
            System.out.println("new Port: " + newPort);
            keyboard = new Scanner(System.in);

           
            socket = new Socket(HOST, Integer.parseInt(newPort));
            SocketOutput = new ObjectOutputStream(socket.getOutputStream());
            SocketInput = new ObjectInputStream(socket.getInputStream());

            
         
        
            SocketOutput.close();
            SocketInput.close();
            socket.close();

        }
         catch (IOException e) {
            System.out.println(e);
        } catch (ClassNotFoundException e) {
            e.printStackTrace();
        }
    }




}

