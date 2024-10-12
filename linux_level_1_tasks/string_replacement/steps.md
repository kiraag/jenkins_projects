Within the Stratos DC, the backup server holds template XML files crucial for the Nautilus application. Before utilization, these files require valid data insertion. As part of routine maintenance, system admins at xFusionCorp Industries employ string and file manipulation commands.

Your task is to substitute all occurrences of the string Random with Echo-Location within the XML file located at `/root/nautilus.xml` on the backup server.

---

## To replace all occurrences of the string `"Random"` with `"Echo-Location"` in the `nautilus.xml` file on the backup server, you can use the `sed` command. Here’s how you can do it:

### Step-by-Step Command:

Log in to the backup server if you're not already logged in.

Run the following command to perform the string substitution:

```bash
sudo sed -i 's/Random/Echo-Location/g' /root/nautilus.xml
```

## Explanation:

- `sed`: Stream editor used for text manipulation.

- `i`: In-place edit, which modifies the file directly.

- `'s/Random/Echo-Location/g'`: This is the substitution command:

    - `s`: Substitute.

    - `Random`: The string to be replaced.

    - `Echo-Location`: The replacement string.

    - `g`: Global flag, which ensures that all occurrences of `"Random"` in the file are replaced, not just the first one.

- `/root/nautilus.xml`: The path to the XML file.

### Verify the Changes:

You can check if the replacements have been applied correctly by using `cat` or `grep`:

```bash
cat /root/nautilus.xml | grep 'Echo-Location'
```
This command will output any lines that contain `"Echo-Location"`, confirming the substitution.