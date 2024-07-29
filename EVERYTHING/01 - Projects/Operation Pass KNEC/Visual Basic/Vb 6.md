### KNEC Exam: Visual Programming (VB6) with Answers

**Time: 2 Hours**

---

#### Section A: Short Answer Questions (40 Marks)

1. **Define the following terms as used in Visual Basic Programming:**
    - **Form module:** A Form module is a type of module in VB that represents the graphical interface of the application. It contains controls such as buttons, text boxes, and labels that the user interacts with.
    - **Application:** An application is a complete, standalone program that performs a specific function for the user. It consists of one or more forms and modules.
    - **Project:** A project in VB is a collection of all files, forms, modules, and resources that make up an application. It is managed through the Visual Basic IDE.

2. **State four factors to consider when naming an object in a visual programming environment.**
    - Clarity: The name should clearly describe the purpose of the object.
    - Consistency: Follow a consistent naming convention throughout the project.
    - Length: The name should be concise but descriptive enough to avoid ambiguity.
    - Uniqueness: Ensure the name is unique within the scope to avoid conflicts.

3. **Explain two reasons that may make the installation of Visual Basic 6.0 unsuccessful on a computer with the following specifications:**
    - **Android operating system:** VB6 is designed for Windows operating systems and is not compatible with Android OS.
    - **32 MB RAM:** VB6 requires more memory to run efficiently. 32 MB RAM is insufficient for installation and operation.
    - **Hard disk space of 116MB:** VB6 requires more disk space for installation and associated files.

4. **Distinguish between the `Name` and `Text` properties of an object in Visual Basic.**
    - **Name Property:** This property sets or returns the name of the object which is used to reference it in code.
    - **Text Property:** This property sets or returns the text displayed by the object, such as the text inside a TextBox.

5. **Outline three properties that can be used with a DataList in a Visual Basic program.**
    - **DataSource:** Sets the source of the data for the DataList.
    - **DataField:** Specifies the field in the data source to bind to the DataList.
    - **BoundColumn:** Determines which column’s value is used as the value of the DataList.

6. **Explain the function of each of the following sections of a Visual Basic DataReport:**
    - **Report footer:** Displays summary information at the end of the report, such as totals or conclusions.
    - **Page footer:** Displays information at the bottom of each page, such as page numbers or dates.

7. **Describe three optional parameters of the `OpenDatabase` method used during a connection.**
    - **Exclusive:** Opens the database in exclusive mode, allowing only one user to access it at a time.
    - **ReadOnly:** Opens the database in read-only mode, preventing any changes to the data.
    - **Connect:** Specifies the type of connection string used to open the database.

8. **State the difference between a conditional loop and an unconditional loop as used in programming.**
    - **Conditional loop:** Executes as long as a specified condition is true (e.g., `While...Wend`, `Do...Loop While`).
    - **Unconditional loop:** Executes a fixed number of times, regardless of any conditions (e.g., `For...Next`).

---

#### Section B: Programming Tasks (30 Marks)

1. **Write a Visual Basic program that displays the sequence of numbers 50, 45, 40, ... 0 on a ListBox together with their cumulative sum using a `While...Wend` loop. Attach the code to a command button.** (5 marks)

    ```vb
    Private Sub Command1_Click()
        Dim num As Integer
        Dim sum As Integer
        num = 50
        sum = 0
        While num >= 0
            List1.AddItem num
            sum = sum + num
            num = num - 5
        Wend
        List1.AddItem "Cumulative Sum: " & sum
    End Sub
    ```

2. **A soda wholesaler sells a 300ml bottle of soda for KSH 25 for less than 200 bottles and KSH 23 per bottle when a customer purchases 200 or more. Write a Visual Basic program that prompts the user for the total number of bottles purchased through the use of a TextBox. The program should then compute the total cost and display the results on a PictureBox.** (8 marks)

    ```vb
    Private Sub Command1_Click()
        Dim bottles As Integer
        Dim cost As Double
        bottles = CInt(Text1.Text)
        If bottles < 200 Then
            cost = bottles * 25
        Else
            cost = bottles * 23
        End If
        Picture1.Print "Total Cost: KSH " & cost
    End Sub
    ```

3. **Write a Visual Basic program that would display the following multiplication table on a form when the number 6 is entered in a TextBox. Use a `For` loop:**
    ```
    6×1=6
    6×2=12
    6×3=18
    6×4=24
    6×5=30
    6×6=36
    ```
    (5 marks)

    ```vb
    Private Sub Command1_Click()
        Dim i As Integer
        Dim num As Integer
        num = CInt(Text1.Text)
        For i = 1 To 6
            List1.AddItem num & " × " & i & " = " & (num * i)
        Next i
    End Sub
    ```

4. **Write a Visual Basic program that allows a user to enter 10 integer values into an array. The program should then sort the values using the bubble sort technique and display the result in a PictureBox. Attach the code to a command button.** (8 marks)

    ```vb
    Private Sub Command1_Click()
        Dim numbers(9) As Integer
        Dim i As Integer
        Dim j As Integer
        Dim temp As Integer
        For i = 0 To 9
            numbers(i) = InputBox("Enter number " & (i + 1))
        Next i
        ' Bubble Sort
        For i = 0 To 8
            For j = 0 To 8 - i
                If numbers(j) > numbers(j + 1) Then
                    temp = numbers(j)
                    numbers(j) = numbers(j + 1)
                    numbers(j + 1) = temp
                End If
            Next j
        Next i
        ' Display sorted numbers
        Picture1.Cls
        For i = 0 To 9
            Picture1.Print numbers(i)
        Next i
    End Sub
    ```

5. **Write a Visual Basic program that calculates the future value (FV) of a property worth PV appreciating at the rate of R% per annum for a period of T years. The formula is given by:**
    \[
    FV = PV \times (1 + \frac{R}{100})^T
    \]
    **The program should use a function to calculate FV when a user enters the values of PV, R, and T in TextBoxes. The program should then display the results in a MessageBox in a currency format. Attach the main procedure to a command button.** (7 marks)

    ```vb
    Private Function CalculateFV(PV As Double, R As Double, T As Double) As Double
        CalculateFV = PV * (1 + R / 100) ^ T
    End Function

    Private Sub Command1_Click()
        Dim PV As Double
        Dim R As Double
        Dim T As Double
        Dim FV As Double
        PV = CDbl(Text1.Text)
        R = CDbl(Text2.Text)
        T = CDbl(Text3.Text)
        FV = CalculateFV(PV, R, T)
        MsgBox "Future Value: " & FormatCurrency(FV)
    End Sub
    ```

---

#### Section C: Analytical Questions (30 Marks)

1. **Explain three types of code stepping features used in a Visual Basic programming language.** (6 marks)
    - **Step Into:** Executes the next line of code and if the line is a call to a procedure, it enters the procedure and pauses on the first line.
    - **Step Over:** Executes the next line of code, but if the line is a call to a procedure, it runs the entire procedure and pauses on the line following the procedure call.
    - **Step Out:** Executes the remaining lines of the current procedure and pauses on the line that called the procedure.

2. **Describe two functions that can be used to format text in a Visual Basic program, excluding the use of commas. Provide examples for each.** (4 marks)
    - **FormatCurrency:** Converts a numeric value to a string formatted as currency.
        ```vb
        Dim amount As Double
        amount = 1234.56
        MsgBox FormatCurrency(amount)
        ```
    - **FormatPercent:** Converts a numeric value to a string formatted as a percentage.
        ```vb
        Dim ratio As Double
        ratio = 0.75
        MsgBox FormatPercent(ratio)
        ```

3. **A programmer was advised to decompose a large module into multiple procedures. Explain two reasons for this.** (4 marks)
    - **Modularity:** Breaking down a large module into smaller procedures makes the code more modular, which enhances readability and maintainability.


#### Section C: Analytical Questions (Continued)

3. **A programmer was advised to decompose a large module into multiple procedures. Explain two reasons for this.** (4 marks)
    - **Modularity:** Breaking down a large module into smaller procedures makes the code more modular, which enhances readability and maintainability. Each procedure can be developed, tested, and debugged independently.
    - **Reusability:** Smaller procedures can be reused across different parts of the application, reducing code duplication and increasing efficiency.

4. **Outline three benefits of using control arrays in a Visual Basic program.** (3 marks)
    - **Reduced Code Complexity:** Control arrays allow for the handling of multiple similar controls using a single set of event procedures, reducing the complexity of the code.
    - **Efficient Resource Management:** Control arrays use fewer resources because they share the same event procedures and memory space.
    - **Dynamic Control Management:** Controls can be dynamically added or removed at runtime, providing flexibility in the user interface.

5. **Write a Visual Basic program that determines the roots of a quadratic equation using the following formula:**
    \[
    x1 = \frac{-b + \sqrt{b^2 - 4ac}}{2a}, \quad x2 = \frac{-b - \sqrt{b^2 - 4ac}}{2a}
    \]
    **Include an error handler with error codes 5 and 6 to test for division by zero and the square root of a negative number, respectively. Display the results in TextBoxes.** (7 marks)

    ```vb
    Private Sub Command1_Click()
        Dim a As Double, b As Double, c As Double
        Dim x1 As Double, x2 As Double
        Dim discriminant As Double
        a = CDbl(Text1.Text)
        b = CDbl(Text2.Text)
        c = CDbl(Text3.Text)
        
        On Error GoTo ErrorHandler
        discriminant = b * b - 4 * a * c
        If discriminant < 0 Then Err.Raise 6 ' Overflow for square root of negative number
        
        x1 = (-b + Sqr(discriminant)) / (2 * a)
        x2 = (-b - Sqr(discriminant)) / (2 * a)
        
        Text4.Text = x1
        Text5.Text = x2
        Exit Sub
        
    ErrorHandler:
        Select Case Err.Number
            Case 11
                MsgBox "Division by zero error."
            Case 6
                MsgBox "Invalid operation: Square root of a negative number."
            Case Else
                MsgBox "Error: " & Err.Description
        End Select
    End Sub
    ```

6. **Explain two effects of using the `Option Explicit` statement in a Visual Basic program.** (2 marks)
    - **Prevents Implicit Variable Declaration:** Forces the programmer to explicitly declare all variables, reducing the chances of typographical errors and improving code clarity.
    - **Improves Debugging:** Helps in catching undeclared variable errors at compile time rather than at runtime, making debugging easier and more efficient.

---

### KNEC Exam: Visual Programming (VB6) Without Answers

**Time: 2 Hours**

---

#### Section A: Short Answer Questions (40 Marks)

1. **Define the following terms as used in Visual Basic Programming:**
    - Form module
    - Application
    - Project

2. **State four factors to consider when naming an object in a visual programming environment.**

3. **Explain two reasons that may make the installation of Visual Basic 6.0 unsuccessful on a computer with the following specifications:**
    - Android operating system
    - 32 MB RAM
    - Hard disk space of 116MB

4. **Distinguish between the `Name` and `Text` properties of an object in Visual Basic.**

5. **Outline three properties that can be used with a DataList in a Visual Basic program.**

6. **Explain the function of each of the following sections of a Visual Basic DataReport:**
    - Report footer
    - Page footer

7. **Describe three optional parameters of the `OpenDatabase` method used during a connection.**

8. **State the difference between a conditional loop and an unconditional loop as used in programming.**

---

#### Section B: Programming Tasks (30 Marks)

1. **Write a Visual Basic program that displays the sequence of numbers 50, 45, 40, ... 0 on a ListBox together with their cumulative sum using a `While...Wend` loop. Attach the code to a command button.** (5 marks)

2. **A soda wholesaler sells a 300ml bottle of soda for KSH 25 for less than 200 bottles and KSH 23 per bottle when a customer purchases 200 or more. Write a Visual Basic program that prompts the user for the total number of bottles purchased through the use of a TextBox. The program should then compute the total cost and display the results on a PictureBox.** (8 marks)

3. **Write a Visual Basic program that would display the following multiplication table on a form when the number 6 is entered in a TextBox. Use a `For` loop:**
    ```
    6×1=6
    6×2=12
    6×3=18
    6×4=24
    6×5=30
    6×6=36
    ```
    (5 marks)

4. **Write a Visual Basic program that allows a user to enter 10 integer values into an array. The program should then sort the values using the bubble sort technique and display the result in a PictureBox. Attach the code to a command button.** (8 marks)

5. **Write a Visual Basic program that calculates the future value (FV) of a property worth PV appreciating at the rate of R% per annum for a period of T years. The formula is given by:**
    \[
    FV = PV \times (1 + \frac{R}{100})^T
    \]
    **The program should use a function to calculate FV when a user enters the values of PV, R, and T in TextBoxes. The program should then display the results in a MessageBox in a currency format. Attach the main procedure to a command button.** (7 marks)

---

#### Section C: Analytical Questions (30 Marks)

1. **Explain three types of code stepping features used in a Visual Basic programming language.** (6 marks)

2. **Describe two functions that can be used to format text in a Visual Basic program, excluding the use of commas. Provide examples for each.** (4 marks)

3. **A programmer was advised to decompose a large module into multiple procedures. Explain two reasons for this.** (4 marks)

4. **Outline three benefits of using control arrays in a Visual Basic program.** (3 marks)

5. **Write a Visual Basic program that determines the roots of a quadratic equation using the following formula:**
    \[
    x1 = \frac{-b + \sqrt{b^2 - 4ac}}{2a}, \quad x2 = \frac{-b - \sqrt{b^2 - 4ac}}{2a}
    \]
    **Include an error handler with error codes 5 and 6 to test for division by zero and the square root of a negative number, respectively. Display the results in TextBoxes.** (7 marks)

6. **Explain two effects of using the `Option Explicit` statement in a Visual Basic program.** (2 marks)