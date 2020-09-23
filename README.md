<div align="center">

## Software Security come back again


</div>

### Description

How to prevent your software from unauthorised access. Some days ago i have written a small trick to 'prevent your program from unauthorised access ' i got good responce for this code . But there is a small bug in that code , the code fails when u use it with a database file. Now i m going to present u a another small trick which can help u for the same . If u r going to use the following code , i request u to please see my previous code. Lastally don't forgot to VOTE because your kind judgement is very useful for all the coders and me.

Here in planet source code i found that there is a very big GAP between Viewers of code and Voters of Code . So please keep Voting the coders.

Assume u r developing a small application for some organisation.It is possible that some one can duplicate the program for his use.So that in such condition use the following code.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Milind Patil](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/milind-patil.md)
**Level**          |Advanced
**User Rating**    |3.7 (22 globes from 6 users)
**Compatibility**  |VB 5\.0, VB 6\.0
**Category**       |[Coding Standards](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/coding-standards__1-43.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/milind-patil-software-security-come-back-again__1-38282/archive/master.zip)





### Source Code

```
Hi Friends ,
  Here is my another code which shows u how to prevent your software from unauthorised access. Some days ago i have written a small trick to 'prevent your program from unauthorised access ' i got good responce for this code . But there is a small bug in that code , the code fails when u use it with a database file. Now i m going to present u a another small trick which can help u for the same . If u r going to use the following code , i request u to please see my previous code. Lastally don't forgot to VOTE because your kind judgement is very useful for all the coders and me.
  Here in planet source code i found that there is a very big GAP between Viewers of code and Voters of Code . So please keep Voting the coders.
Assume u r developing a small application for some organisation.It is possible that some one can duplicate the program for his use.So that in such condition use the following code.
BASIC INFORMATION NEEDED - : Fristally u needed the 'Serial Number' of the Customer's drive .
			   It may look like 2E332-32FFW.U can see this also from dos shell	    			   by using command DIR.
Now simplly pest the following code in FORM_load() event.
What the code does ???
   The code matches the Drive serial number with the serial number given in code . It the serial number don't match , It quit's the program.
'--------------------------
CODE - :
'Programmer - Milind M. Patil
'Date       - 22/07/2002
Private Sub Form_Load()
Dim serial As String
Dim serial2 As String
serial = "3C6E-1BF2"
Dim volname As String  ' receives volume name of C:
Dim sn As Long     ' receives serial number of C:
Dim snstr As String   ' display form of serial number
Dim maxcomplen As Long ' receives maximum component length
Dim sysflags As Long  ' receives file system flags
Dim sysname As String  ' receives the file system name
Dim retval As Long   ' return value
' Initialize string buffers.
volname = Space(256)
sysname = Space(256)
' Get information about the C: drive's volume.
retval = GetVolumeInformation("c:\", volname, Len(volname), sn, maxcomplen, _
  sysflags, sysname, Len(sysname))
' Remove the trailing nulls from the two strings.
volname = Left(volname, InStr(volname, vbNullChar) - 1)
sysname = Left(sysname, InStr(sysname, vbNullChar) - 1)
' Format the serial number properly.
snstr = Trim(Hex(sn))
snstr = String(8 - Len(snstr), "0") & snstr
snstr = Left(snstr, 4) & "-" & Right(snstr, 4)
' Display the volume name, serial number, and file system name.
Debug.Print "Volume Name: "; volname
Debug.Print "Serial Number: "; snstr
Debug.Print "File System: "; sysname
Text1.Text = snstr
serial2 = Text1.Text
If serial <> serial2 Then
 MsgBox "Sorry You are not Authorised User of This Program", vbCritical, "Developed By Milind M. Patil , Keep your planet clean"
 Unload Me
Else
End If
End Sub
'---------------------
```

