# Welcome to my Page

Repos:
- [ScrapEngine](https://github.com/Ranchonyx/ScrapEngine)
A thing.

- [OnyxLib](https://github.com/Ranchonyx/OnyxLib)
A library of functions and other useful modules including one for face recognition.

- [Informatik](https://github.com/Ranchonyx/Informatik)
The repository for my high school homework.

- [frameCap](https://github.com/Ranchonyx/frameCap)
An application for extracting frames from an .mkv video

- [occurrences](https://github.com/Ranchonyx/occurrences)
Creative name, I know. Counts word occurrences in a as parameter give file.
Supports .txt, crazy, I know

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
