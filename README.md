# BCA2022-23 CSharp Programs

# 1. Addition Of 2 Numbers
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Demo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.BackgroundColor = ConsoleColor.White;
            Console.ForegroundColor = ConsoleColor.Black;
            Console.Clear();
            int a, b;
            Console.Write("Enter Value For A:");
            a= Convert.ToInt32(Console.ReadLine());
            Console.Write("Enter Value For B:");
            b= Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("Total is : "+(a+b));
            Console.Read();
        }
    }
}
```
## OUTPUT   

![image](https://user-images.githubusercontent.com/31475304/204727537-03fa383e-f335-4943-860d-7bcfc1d6df60.png)

# 2. Find Max / Equal Using 2 Numbers
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Demo1
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int n1,n2;
            Console.WriteLine("Enter First Value");
            n1= int.Parse(Console.ReadLine());
            Console.WriteLine("Enter Second Value");
            n2= int.Parse(Console.ReadLine());
            if(n1<n2)
            {
                Console.WriteLine("N2 is Max");
            }
            else if(n1 == n2)
            {
                Console.WriteLine("Both Are Equal");
            }
            else
            {
                Console.WriteLine("N1 is Max");
            }
            Console.Read();
        }
    }
}
```
## OUTPUT

![image](https://user-images.githubusercontent.com/31475304/205203888-afe84ab8-8d8b-4326-882f-83678dfe3f95.png)

# 3. Boxing And Unboxing
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Demo1
{
    internal class Program
    {
        static void Main(string[] args)
        {
            int a = 10;

            object obj;

            obj= a;//Boxing
            Console.WriteLine(obj);
            int b = (int)obj;//Unboxing
            Console.WriteLine(b);
            Console.Read();
        }
    }
}
```
## OUTPUT
![image](https://user-images.githubusercontent.com/31475304/205205701-2f97850a-2881-49eb-8843-0a6d9fdfc773.png)

# 4 . Rectangular Array
```
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Demo1
{
    internal class Program
    {
        static void Main(string[] args)
        {
            Console.Write("Enter Array Size : ");
            int count = Convert.ToInt32(Console.ReadLine());
            int[,] array = new int[count,count];
            for(int i = 0; i < count;i++) 
            {
                for (int j = 0; j < count; j++)
                {
                    Console.Write("Enter Value For Array " + i+""+j + ":");
                    array[i,j] = Convert.ToInt32(Console.ReadLine());
                }
            }
            foreach(int i in array)
            {
                Console.WriteLine(i);
            }
            Console.Read();
        }
    }
}
```
## OUTPUT
![image](https://user-images.githubusercontent.com/31475304/205809771-43359f63-17b5-40c2-b6d3-aa27a638d679.png)

# 5 . Notepad
```
using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;

namespace NotepadDiv_B
{
    public partial class Form1 : Form
    {
        int count;
        string fnm;
        public Form1()
        {
            InitializeComponent();
        }

        private void newToolStripMenuItem_Click(object sender, EventArgs e)
        {
            if(richTextBox1.Text.Length > 0) 
            {
                int a = Convert.ToInt32(MessageBox.Show("Do you want to save?","Notepad",MessageBoxButtons.YesNo,MessageBoxIcon.Question));
                if(a==7)
                {
                    richTextBox1.Text = "";
                    
                    this.Text = "Untitled - Notepad";
                }
                else
                {
                    SaveFileDialog sf = new SaveFileDialog();
                    sf.DefaultExt = "txt";
                    sf.Filter = "Text files (*.txt)|*.txt|All files (*.*)|*.*";
                    sf.ShowDialog();
                    if (sf.FileName != "")
                    {
                        fnm = sf.FileName;
                        richTextBox1.SaveFile(sf.FileName);
                        richTextBox1.Text = "";
                    }
                }
            }
        }

        private void saveToolStripMenuItem_Click(object sender, EventArgs e)
        {
            if (fnm != null)
            {
                richTextBox1.SaveFile(fnm);
                this.Text = fnm;
                count = richTextBox1.Text.Length;
            }
            else
            {
                SaveFileDialog sf = new SaveFileDialog();
                sf.Title = "Save";
                sf.DefaultExt = "txt";
                sf.Filter = "Text files (*.txt)|*.txt|All files (*.*)|*.*";
                sf.ShowDialog();
                if (sf.FileName != "")
                {
                    fnm = sf.FileName;
                    richTextBox1.SaveFile(sf.FileName);
                    this.Text = sf.FileName + " - Notepad";
                    count = richTextBox1.Text.Length;
                }
            }
        }

        private void openToolStripMenuItem_Click(object sender, EventArgs e)
        {
            OpenFileDialog of = new OpenFileDialog();
            of.DefaultExt = "txt";
            of.Filter = "Text files (*.txt)|*.txt|All files (*.*)|*.*";
            of.ShowDialog();
            if (of.FileName != "")
            {
                richTextBox1.LoadFile(of.FileName);
                fnm = of.FileName;
                this.Text = of.FileName + " - Notepad";
                count = richTextBox1.TextLength;
                saveToolStripMenuItem.Enabled = false;               
            }
        }

        private void exitToolStripMenuItem_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void backColorToolStripMenuItem_Click(object sender, EventArgs e)
        {
            ColorDialog cd = new ColorDialog();
            cd.ShowDialog();
            richTextBox1.BackColor = cd.Color;
        }

        private void foreColorToolStripMenuItem_Click(object sender, EventArgs e)
        {
            ColorDialog cd = new ColorDialog();
            cd.ShowDialog();
            richTextBox1.ForeColor = cd.Color;
        }

        private void fontToolStripMenuItem_Click(object sender, EventArgs e)
        {
            FontDialog fd = new FontDialog();
            fd.ShowDialog();
            richTextBox1.Font = fd.Font;
        }
        private void Form1_Load(object sender, EventArgs e)
        {
            this.Text = "Untitled";
        }

        private void richTextBox1_TextChanged(object sender, EventArgs e)
        {
            if (fnm == null)
            {
                this.Text = "Untitled - Notepad *";      
            }
            else
            {
                int count1 = richTextBox1.TextLength;
                if (count != count1)
                {
                    this.Text = fnm + "*";
                    saveToolStripMenuItem.Enabled = true;
                }
                else
                {
                    this.Text = fnm;
                    saveToolStripMenuItem.Enabled = false;
                }
            }
        }

        private void Form1_FormClosing(object sender, FormClosingEventArgs e)
        {
            if(richTextBox1.Text!="")
            {
                int count1 = richTextBox1.TextLength;
                if (count != count1)
                {
                    int a = Convert.ToInt32(MessageBox.Show("Do you want to save?", "Notepad", MessageBoxButtons.YesNo, MessageBoxIcon.Question));
                    if (a == 6)
                    {
                        if (fnm == null)
                        {
                            SaveFileDialog sf = new SaveFileDialog();
                            sf.DefaultExt = "txt";
                            sf.Filter = "Text files (*.txt)|*.txt|All files (*.*)|*.*";
                            sf.ShowDialog();
                            if (sf.FileName != "")
                            {
                                fnm = sf.FileName;
                                richTextBox1.SaveFile(sf.FileName);
                                count = richTextBox1.Text.Length;                               
                            }
                        }
                        else
                        {
                            MessageBox.Show(fnm);
                            richTextBox1.SaveFile(fnm);
                            count = richTextBox1.Text.Length;
                        }
                        this.Close();
                    }
                }
                
            }
        }
    }
}
```
## OUTPUT
![image](https://user-images.githubusercontent.com/31475304/210297915-85a679e0-7a9d-4ea9-88b1-da7706fdc63c.png)
