# PBO_Tugas_6

**Kelas SupportSystem**
`````
import java.util.Scanner;

public class SupportSystem {
    private InputReader reader;
    private Responder responder;
    
    public SupportSystem(){
        reader = new InputReader();
        responder = new Responder();
    }

    public void start(){
        boolean finished = false;
        System.out.println("Selamat datang di Christo Support System.");
        System.out.println("Silakan ceritakan masalah Anda.");
        System.out.println("Kami akan membantu dengan masalah apa pun yang Anda miliki.");
        System.out.println("Ketik 'bye' untuk keluar dari sistem kami.");

        while (!finished){
            String input = reader.getInput();
            if (input.equals("bye")){
                finished = true;
            } else {
                String response = responder.generateResponse();
                System.out.println(response);
            }
        }

        System.out.println("Goodbye! Thank you for using the support system.");
    }

    public static void main(String[] args){
        SupportSystem support = new SupportSystem();
        support.start();
    }
}
`````
**Kelas InputReader**
`````
import java.util.Scanner;

public class InputReader {
    private Scanner scanner;

    public InputReader(){
        scanner = new Scanner(System.in);
    }

    public String getInput(){
        System.out.print("> ");
        return scanner.nextLine();
    }
}
`````

**Kelas Responder**
`````
import java.util.Random;

public class Responder {
    private String[] responses;

    public Responder(){
        responses = new String[]{
            "Itu terdengar menarik. Ceritakan lebih lanjut...",
            "Oh, saya mengerti. Bisakah Anda menjelaskan lebih lanjut?",
            "Hmm, itu cukup rumit. Mari kita bahas lebih dalam.",
            "Menarik. Bisakah Anda memberikan lebih banyak detail?",
            "Biarkan saya berpikir... Bisakah Anda memperjelas sedikit lebih banyak?"
        };
    }

    public String generateResponse(){
        Random random = new Random();
        int index = random.nextInt(responses.length);
        return responses[index];
    }
}
`````
