WEEK 4 : Metadata and File Analysis Report

1. Ocean.jpg
<img width="943" height="631" alt="image" src="https://github.com/user-attachments/assets/b65b4ca3-f1d6-40ea-a12e-342b75cddb5e" />
I analyzed ocean.jpg to see if any flags were hidden within its background data. I used an online tool called exif.tools to browse the file's metadata. By inspecting the output, I found a specific field labeled "Comment". This section explicitly contained the string "THIS IS THE HIDDEN FLAG," which served as the first discovery.

2. dog.jpg
<img width="1005" height="799" alt="image" src="https://github.com/user-attachments/assets/32b01080-2851-4a66-b902-c9336e1b4fa3" />
The next task involved dog.jpg, which I analyzed using the Linux command line on a Kali Linux machine. First, I ran the binwalk command to scan the image, which revealed a hidden Zip archive and a file named hidden_text.txt embedded within the image data. To access this, I used binwalk -e to extract the hidden files into a new directory named _dog.jpg.extracted. After navigating into that folder and using the ls command to confirm the files, I used cat hidden_text.txt to read the contents. This successfully revealed the hidden flag: "THIS IS A HIDDEN FLAG".

3. Solitaire
<img width="1005" height="428" alt="image" src="https://github.com/user-attachments/assets/15c24bbe-ae44-4a64-978c-3d3f833859d0" />
For the third file, solitaire.exe, the goal was to verify if the file was actually an executable. I used the file command in the terminal to check its true signature. The system reported that the file was actually PNG image data with a resolution of 640 x 449, proving the .exe extension was a decoy. To fix this, I used the mv command to rename it to solitaire.png. Finally, I opened the file using the ristretto image viewer to see the actual image of playing cards.
<img width="553" height="418" alt="image" src="https://github.com/user-attachments/assets/cb275997-a96a-4c74-87f8-98ec15dbd4cb" />

4. Rubiks
<img width="740" height="194" alt="image" src="https://github.com/user-attachments/assets/71470ce2-fa9c-4be9-8b78-951bc366280d" />
The analysis of rubiks.jpg followed a similar process to identify another extension mismatch. When I ran the file command on it, the output confirmed that it was also PNG image data rather than a JPEG. I used the mv command to change the extension to .png to match its true format. Once the extension was corrected, I was able to open it with the ristretto tool, which displayed a 3D graphic of a Rubik's Cube.
<img width="586" height="614" alt="image" src="https://github.com/user-attachments/assets/52300c0c-c2a3-49ff-bfa4-94cb02b5e40c" />

5. computer.png
<img width="1068" height="403" alt="image" src="https://github.com/user-attachments/assets/43d4d798-5350-476e-9e18-7e29d0adf548" />
The final part of the lab involved computer.jpg, where I needed to inspect the raw binary data. I first uploaded the file to hexed.it, a web-based hex editor, to view the file headers and hexadecimal values.
<img width="1058" height="513" alt="image" src="https://github.com/user-attachments/assets/1be51d28-9418-4018-9ddb-ab0bf89e669a" />
To make the data more readable, I also used the dCode Strings Extractor tool. By processing the file through this tool, I was able to pull out human-readable text strings from the binary code, such as ICC_PROFILE and mntrRGB XYZ. This demonstrated how a combination of hex editing and string extraction can be used to analyze a file's internal structure.
