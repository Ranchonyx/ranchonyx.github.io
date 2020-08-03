# Welcome to my Page

Check out my GitHub here:
[Ranchonyx](https://github.com/Ranchonyx)

Send me an Email here:
[Felix Janetzki](mailto:felixjanetzki@gmail.com?subject=[GitHub Contact])

Ping me on Discord here:
[Kraut#2929](https://discordapp.com/users/168778401249755137)

Repos:
- [ScrapEngine](https://github.com/Ranchonyx/ScrapEngine)
A thing.

- [OnyxLib](https://github.com/Ranchonyx/OnyxLib)
A library of functions and other useful modules including one for face recognition.

- [Informatik](https://github.com/Ranchonyx/Informatik)
The repository for my high school homework.

- [frameCap](https://github.com/Ranchonyx/frameCap)
An application for extracting frames from an .mkv video

- [Occurrences](https://github.com/Ranchonyx/occurrences)
Creative name, I know. Counts word occurrences in a as parameter give file.

- [CMDDL](https://github.com/Ranchonyx/CMDDL)
A simple command line downloader for all file types.

- [LWJBB](https://github.com/Ranchonyx/LWJBB)
Super lightweight (still java so idk) web browser/content displayer using swing and javafx.

### A sample of my coding style.
> This is the code for an application that counts occurrences of words in a text file.

```java
import java.io.*;
import java.util.HashMap;
import java.util.stream.Collectors;

public class Main {
    public static void main(String[] args) throws IOException {
        try {

            if(args[0].equals("-h") || args[0].equals("--help") || args[0].equals("/?")) {
                System.out.println("Usage: java -jar occurrences.jar <path: String>");
                System.exit(0);
            }

            String path = args[0];
            BufferedReader br = new BufferedReader(new FileReader(path));
            String content = br.lines().collect(Collectors.joining(System.lineSeparator()));
            br.close();

            String[] words = content.replaceAll(",","").replaceAll("\\.","").replaceAll("\n","").split(" ");
            HashMap<String, Integer> occurrenceMap = new HashMap<String, Integer>();

            for(String w : words) {
                if(occurrenceMap.containsKey(w)) {
                    occurrenceMap.put(w, occurrenceMap.get(w)+1);
                } else {
                    occurrenceMap.put(w, 1);
                }
            }

            for (String key : occurrenceMap.keySet()) {
                System.out.println(key+" : "+occurrenceMap.get(key));
            }

        } catch (ArrayIndexOutOfBoundsException arrayIndexOutOfBoundsException) {
            System.out.println("No path argument given, exiting.");
            System.exit(1);
        }

    }
}

```
