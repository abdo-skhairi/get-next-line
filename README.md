![ALt text](https://raw.githubusercontent.com/abdo-skhairi/get-next-line/refs/heads/main/image.png)

### Steps to Implement get_next_line:

1. **📂 Function Input**:
   - The function should accept a file descriptor (an integer representing an open file) as its input.

2. **🗃️ Define a Static Buffer**:
   - Use a **static buffer** to store data between function calls. This allows the function to handle partially read data efficiently.
   - A buffer size (e.g., `BUFFER_SIZE`) should be defined for how much data is read at a time.

3. **🔄 Read Data from the File Descriptor**:
   - Use the `read()` system call to read raw bytes from the file descriptor into the buffer.
   - Append the newly read data to any leftover data from the previous call.

4. **🔍 Search for a Line Break**:
   - Look for a newline character (`\n`) in the buffer.
   - If a newline is found:
     - Extract the portion of the buffer up to (and including) the newline.
     - Save any remaining data after the newline for the next function call.

5. **📄 Handle the End of the File**:
   - If the `read()` call returns 0 (indicating the end of the file) and there is still data in the buffer, return that data as the last line.
   - If `read()` returns 0 and the buffer is empty, return `NULL`.

6. **⚠️ Handle Errors**:
   - If `read()` returns `-1`, handle errors appropriately and return `NULL`.

7. **🔄 Return a Dynamically Allocated String**:
   - Each call to `get_next_line` should return a newly allocated string containing the next line, which the caller is responsible for freeing.

8. **🧹 Memory Management**:
   - Ensure proper memory allocation and freeing for temporary and dynamic buffers.
   - Avoid memory leaks by cleaning up the static buffer when the file is fully read.

## 📬 Contact Me

- 📧 **Email:** skhairi.abderahmane@gmail.com  
- 📸 **Instagram:** [@abdo.skh](https://instagram.com/abdo.skh)

---
