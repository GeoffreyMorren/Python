<h1 align="center">Algorithm for File Updates in Python</h1>

<h2 align="center">Project Description</h2>

<p align="center">You are a security professional working at a health care company. As part of your job, you're required to regularly update a file that identifies the employees who can access restricted content. The contents of the file are based on who is working with personal patient records. Employees are restricted access based on their IP address. There is an allow list for IP addresses permitted to sign into the restricted subnetwork. There's also a remove list that identifies which employees you must remove from this allow list.</p>

<h3 align="center">Open the File that Contains the Allow List</h3>

<p align="center"><img src="https://github.com/GeoffreyMorren/Python/assets/152500568/0c3f231d-ca3e-45a4-9ea9-ad477d4e0437" alt="Image 1"></p>

<p align="center"><code>import_file</code> is assigned the name of the file we want to open, which is "allow_list.txt".</p>
<p align="center"><code>remove_list</code> is assigned a list of IP addresses that are no longer allowed to access restricted information.</p>
<p align="center">The <code>with open(import_file, "r") as file:</code> statement opens the specified file in read mode ("r") using a ‘with’ statement, which ensures that the file is properly closed after we're done with it. The file is opened with the name ‘file’ as an object, which we can use to perform operations on the file.</p>

<h3 align="center">Read the File Contents</h3>

<p align="center"><img src="https://github.com/GeoffreyMorren/Python/assets/152500568/800419ee-8cdb-4269-a4bf-427245c9d1c8" alt="Image 2"></p>

<p align="center">Inside the <code>with</code> block, <code>file.read()</code> reads the contents of the file and stores it in the variable <code>ip_addresses</code>.</p>
<p align="center">The <code>print(ip_addresses)</code> statement displays the content of the file on the console.</p>

<h3 align="center">Convert the String into a List</h3>

<p align="center"><img src="https://github.com/GeoffreyMorren/Python/assets/152500568/3d31c0fe-75ff-463f-839f-4125065e12b9" alt="Image 3"></p>

<p align="center"><code>ip_addresses.split()</code> is used to split the string into a list, using whitespace as the default separator, so that each IP address is a separate element in the list.</p>

<h3 align="center">Iterate through the Remove List</h3>

<p align="center"><img src="https://github.com/GeoffreyMorren/Python/assets/152500568/3f8961e1-191f-40a9-9feb-28f139a95a0d" alt="Image 4"></p>

<p align="center">The subsequent <code>for</code> loop iterates through the elements in the <code>ip_addresses</code> list, and <code>print(element)</code> displays each element (IP address) in every iteration.</p>

<h3 align="center">Remove IP Addresses that are on the Remove List</h3>

<p align="center"><img src="https://github.com/GeoffreyMorren/Python/assets/152500568/e482002a-a30e-45b5-9e65-1153ebd584d2" alt="Image 5"></p>

<p align="center">Within the <code>for</code> loop, a conditional statement checks if the current element is in <code>remove_list</code>, and if it is, the element is removed from <code>ip_addresses</code>.</p>
<p align="center">Finally, <code>print(ip_addresses)</code> displays the modified <code>ip_addresses</code> list, with the specified IP addresses removed.</p>

<h3 align="center">Update the File with the Revised List of IP Addresses</h3>

<p align="center"><img src="https://github.com/GeoffreyMorren/Python/assets/152500568/a5c55094-daec-452c-a876-8c1c03a6c70b" alt="Image 6"></p>

<p align="center">The section of code converts the modified <code>ip_addresses</code> list back into a string with newline separation using <code>"\n".join(ip_addresses)</code>.</p>
<p align="center">A second <code>with</code> statement is used to open the original file in write mode ("w"), and <code>file.write(ip_addresses)</code> is used to rewrite the file with the modified contents.</p>

<h2 align="center">Summary</h2>

<p align="center">Reading a File: It starts by opening a file named "allow_list.txt" for reading, using the <code>with open(import_file, "r") as file:</code> construct. The file's content is read and stored in a variable named <code>ip_addresses</code>.</p>

<p align="center">Converting to a List: The content stored in <code>ip_addresses</code> is then split into a list of IP addresses using the <code>split()</code> method, which separates the addresses based on whitespace or newlines.</p>

<p align="center">Filtering IP Addresses: The algorithm uses a <code>for</code> loop to iterate through the <code>ip_addresses</code> list. It checks each IP address against a <code>remove_list</code> to see if it should be removed from the list. If an IP address is found in the <code>remove_list</code>, it is removed from <code>ip_addresses</code>.</p>

<p align="center">Converting Back to String: After filtering, the modified <code>ip_addresses</code> list is converted back into a single string with newline separation using the <code>join()</code> method.</p>

<p align="center">Writing to the File: The algorithm opens the same file ("allow_list.txt") for writing, replacing its original contents with the modified <code>ip_addresses</code> string using the <code>write()</code> method.</p>
