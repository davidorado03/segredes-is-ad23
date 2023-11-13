# vault-door-training

## Objetivo
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java)
## Solución
```bash
┌──(kali㉿kali)-[~/retos/reversing/parte1/vault-door-training]
└─$ wget https://jupiter.challenges.picoctf.org/static/1afdf83322ee9c0040f8e3a3c047e18b/VaultDoorTraining.java
--2023-11-12 19:39:59--       

2023-11-12 19:40:01 (13.7 MB/s) - ‘VaultDoorTraining.java’ saved [943/943]

┌──(kali㉿kali)-[~/retos/reversing/parte1/vault-door-training]
└─$ cat VaultDoorTraining.java 
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
        Scanner scanner = new Scanner(System.in); 
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
   }

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_eec0716b713");
    }
}

┌──(kali㉿kali)-[~/retos/reversing/parte1/vault-door-training]
└─$ java --version              
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
openjdk 17.0.8 2023-07-18
OpenJDK Runtime Environment (build 17.0.8+7-Debian-1)
OpenJDK 64-Bit Server VM (build 17.0.8+7-Debian-1, mixed mode, sharing)

┌──(kali㉿kali)-[~/retos/reversing/parte1/vault-door-training]
└─$ javac --version
Command 'javac' not found, did you mean:
  command 'javagc' from deb libbpf-tools
  command 'javacc' from deb javacc
Try: sudo apt install <deb name>

┌──(kali㉿kali)-[~/retos/reversing/parte1/vault-door-training]
└─$ java VaultDoorTraining.java
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Enter vault password: picoCTF{w4rm1ng_Up_w1tH_jAv4_eec0716b713}
Access granted.

```
## Notas adicionales

## Referencias