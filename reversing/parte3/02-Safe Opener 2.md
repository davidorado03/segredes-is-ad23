# Safe Opener 2

## Objetivo
What can you do with this file?I forgot the key to my safe but this [file](https://artifacts.picoctf.net/c/292/SafeOpener.class) is supposed to hel
## Solución
```bash
Decompilamos el archivo que nos dan en https://www.decompiler.com/jar/d55e38bd06134757bd5cfd5a9676a73a/SafeOpener.java

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.util.Base64;
import java.util.Base64.Encoder;

public class SafeOpener {
   public static void main(String[] args) throws IOException {
      BufferedReader keyboard = new BufferedReader(new InputStreamReader(System.in));
      Encoder encoder = Base64.getEncoder();
      String encodedkey = "";
      String key = "";

      for(int i = 0; i < 3; ++i) {
         System.out.print("Enter password for the safe: ");
         key = keyboard.readLine();
         encodedkey = encoder.encodeToString(key.getBytes());
         System.out.println(encodedkey);
         boolean isOpen = openSafe(encodedkey);
         if (isOpen) {
            break;
         }

         System.out.println("You have  " + (2 - i) + " attempt(s) left");
      }

   }

   public static boolean openSafe(String password) {
      String encodedkey = "picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_0e57c117}";
      if (password.equals(encodedkey)) {
         System.out.println("Sesame open");
         return true;
      } else {
         System.out.println("Password is incorrect\n");
         return false;
      }
   }
}

picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_0e57c117}
```
## Notas adicionales

## Referencias