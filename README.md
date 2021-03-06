# 1.Running then compiling in Ada

### Compiling
Let us consider main_mine.adb as our program. Then ```gnatmake main_mine.adb``` is the simplest form. By default, the executable output of "main_mine.adb" is "main_mine". To be more precise, if we consider,
- ```prog_path```, the directory where to put the products of the compilation;
- ```exe_dir```, where to put the executable file;
- ```myMain.exe```, or any other name, for this produced executable program,

then, to compile, we write,
```shell
gnatmake main_mine.adb -D prog_path -o exe_dir/myMain.exe
```


### Running
```Bash
./myMain.exe
```



# 2. Anatomy of an Ada program

## 2.a. Programs & subprograms

You have three entities in Ada, which is object oriented, the function, the procedure and the package which can include many functions and procedures. For the purpose of illustration, we consider, respectively, ```my_func.adb```, ```my_proc.adb``` and ```my_packge```. The name of the program, cf. [ARM](link_here), should be the same as the entity's one. In their simplest form, with no parameter,

### Function
File :```my_func.adb```

```Ada
with Ada.Text_IO;   use Ada.Text_IO;    -- the "with / use" clauses part


procedure my_func is                    -- Procedure, function, package's name must be the file's one
  val1 : float  := 11;                  -- Variables declaration
begin
  -- Some instructions                  -- the program's instructions
end my_func
  ```

### Procedure
File :```my_proc.adb```
```Ada
with Ada.Text_IO;   use Ada.Text_IO;    -- the with / use clauses part

procedure my_proc is
  sum : Float :=  3.1415;               -- Variables declaration's part
  ...
begin
  --Some instructions                   -- Instructions part
end my_proc
```


### Package
Specification package's name : ```my_pack.ads```
```Ada
with ... Patience is mother of success 
```




+ Directory :: ZX_function_procedure_package




### Nota Bene
• On the 'main' procedure/program
In Ada, the main procedure does not need to be called 'main', any name can be given.

• To get the full picture, Ada is a high integrity programming language. Functions and procedures are included in a package
Hence, along with the ```*.adb```, Ada Body package, ```anatomy_program.adb```, comes a second file, the ```Ada Specification package```, ```*.ads```, named
```Ada
anatonmy-program.ads
```
However, this does not prevent you to create single procedure or function files if needed, depending on your needs.


## 2.b. About *with, use, renames*

- A ```with``` clause makes the content of a package visible by selection,
```Ada
        with Ada.Text_IO;
        ..
            Ada.Text_IO.Put_Line("Hello, World");
 ```
            
- A 'use' clause makes all the content of a package directly visible. Less typing and less readability.

        with Ada.Text_IO;
        use Ada.Text_IO;
        ..
        Put_Line("Hello_World");
    

- By renaming, we get a shorter alias to any package name

        with Ada.Text_IO;
        
        procedure ..
            package IO renames Ada.Text_IO;
        begin
            IO.Put_Line("Hello, renames");
            


### General rule
For a better maintenance, improved readability, one is always suggested to use:
- ```use``` for the most 'obvious' packages (define obvious);
- ```renames``` for all other packages.


# 3. The *Hello World* program

```Ada
with Ada.Text_IO;
...
```


# 4. Help and References
-- Here!
