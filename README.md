make sure to follow these steps:

Go to the official SourceForge mirror: https://sourceforge.net/projects/json-java.mirror/files/20240205/org.json-1.6-20240205.jar/download
//------------------------------------------------------------------------------------------
Save the file into your project folder under a new directory called lib/.
//-------------------------------------------------------------------------------
Open .vscode/settings.json in your project root. Add
{
  "java.project.referencedLibraries": [
    "lib/**/*.jar"
  ]
}
//----------------------------------------------------------------------------
Reload VS Code
Press Ctrl+Shift+P → type Java: Clean Java Language Server Workspace → Enter.

Restart VS Code.

The red underline on import org.json.JSONObject; should disappear.
//----------------------------------------------------------------

Create a simple test class

package pack;

import org.json.JSONObject;

public class testClass {
    public static void main(String[] args) {
        JSONObject obj = new JSONObject();
        obj.put("cin", "ABC123");
        obj.put("nom", "Ali");
        System.out.println(obj.toString(2));
    }
}
//---------------------------------------------
Compile and Run
javac -cp "lib/org.json-1.6-20240205.jar;src" src/pack/testClass.java
java -cp "lib/org.json-1.6-20240205.jar;src" pack.testClass

Expected Output:
{
  "cin": "ABC123",
  "nom": "Ali"
}


