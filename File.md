using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using System.Runtime.InteropServices;
using System.IO;

namespace Systemworks_ESO_Project
{
    public partial class Form1 : Form
    {
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            // Comment Commands
            if (NumberRight.Text.StartsWith("//") == true)
            {
                MessageBox.Show(NumberRight.Text, "Comment", MessageBoxButtons.OK, MessageBoxIcon.Question);
                return;
            }



            // Commands (Close App)
            if (NumberRight.Text == "Close App")
            {
                if (MessageBox.Show("This command will change settings of the application. Please conform these actions (Following Actions: Close Application) (Warning Code: VALIDATIONSETINGSCONFORM)", "Warning", MessageBoxButtons.YesNo, MessageBoxIcon.Warning) == DialogResult.Yes)
                {
                    Application.Exit();
                    return;
                }
                else
                {
                    MessageBox.Show("The command was aboarted.", "Warning", MessageBoxButtons.OK, MessageBoxIcon.Warning);
                    return;
                }
            }
            else
            {
                if (NumberRight.Text == "Change Quality")
                {
                    if (MessageBox.Show("This command will change settings of the application. Please conform these actions (Following Actions: Quality Menu) (Warning Code: VALIDATIONSETINGSCONFORM)", "Warning", MessageBoxButtons.YesNo, MessageBoxIcon.Warning) == DialogResult.Yes)
                    {
                        MessageBox.Show("There is no quality settings available; all settings are kept the same.", "Warning", MessageBoxButtons.OK, MessageBoxIcon.Warning);
                        return;
                    }
                    else
                    {
                        MessageBox.Show("The command was aboarted.", "Warning", MessageBoxButtons.OK, MessageBoxIcon.Warning);
                        return;
                    }



                }
            }
            if (NumberRight.Text == "Info")
            {
                MessageBox.Show("Systemworks ESO Project is a project where you can type and do stuff like entering commands and much more, you can configure the project with some commands as well, else. Do them Manually", "Info", MessageBoxButtons.OK, MessageBoxIcon.Information);
                return;
            }

            if (NumberRight.Text.StartsWith("DoUsage") == true)
            {
                NumberRight.Text = "Unknown";
            }

            if (NumberRight.Text == "Get Quality")
            {
                if (MessageBox.Show("This command will change settings of the application. Please conform these actions (Following Actions: Quality Menu (Get Value))", "Warning", MessageBoxButtons.YesNo, MessageBoxIcon.Warning) == DialogResult.Yes)
                {
                    MessageBox.Show("10 (original set)", "Warning", MessageBoxButtons.OK, MessageBoxIcon.Warning);
                    return;
                }
                else
                {
                    MessageBox.Show("The command was aboarted.", "Warning", MessageBoxButtons.OK, MessageBoxIcon.Warning);
                    return;
                }
            }
            else
            {
                MessageBox.Show("Current Input cannot run; The command string dosn't exist (Error Code: AN012455)", "Error", MessageBoxButtons.OK, MessageBoxIcon.Error);
                return;

            }

            
        }

                     

        private void button2_Click(object sender, EventArgs e)
        {
            NumberRight.Text = "";
        }

        private void button3_Click(object sender, EventArgs e)
        {
            
            if (NumberRight.Text.StartsWith ("//") == true)
            {
                NumberRight.Text = "// Comment?";
                groupBox1.Visible = true;
            }

            if (NumberRight.Text.StartsWith("//") == false)
            {
                NumberRight.Text = "Input";
                groupBox1.Visible = false;
            }
        }

        private void NumberRight_Load(object sender, EventArgs e)
        {
            if (NumberRight.Text.StartsWith ("//") == true)
            {
                NumberRight.Text = "// Comment?";
            }
        }

        private void listBox1_SelectedIndexChanged(object sender, EventArgs e)
        {

        }

        private void button4_Click(object sender, EventArgs e)
        {
            if (NumberRight.Text.StartsWith("//") == false)
            {
                if (MessageBox.Show("The Comment Prefix is not in the input. Verify If you want to add a comment to the input", "Warning", MessageBoxButtons.YesNo, MessageBoxIcon.Warning) == DialogResult.Yes)
                {
                    NumberRight.Text = "// Comment?";
                }
                else
                {
                    MessageBox.Show("Verification canclled", "Canclled");
                    return;
                }
            }

            if (NumberRight.Text.StartsWith("//") == true)
            {
                NumberRight.Text = "// Comment?";
            }
        }

        private void groupBox1_Enter(object sender, EventArgs e)
        {
            if (NumberRight.Text.StartsWith ("//") == false)
            {
                if (MessageBox.Show("The Comment Prefix is not in the input. Verify If you want to add a comment to the input", "Warning", MessageBoxButtons.YesNo, MessageBoxIcon.Warning) == DialogResult.Yes)
                {
                    NumberRight.Text = "// Comment?";
                }
                else
                {
                    MessageBox.Show("Verification canclled", "Canclled");
                    return;
                }
            }
        }

        private void groupBox2_Enter(object sender, EventArgs e)
        {

        }

        private void linkLabel1_LinkClicked(object sender, LinkLabelLinkClickedEventArgs e)
        {
            System.Diagnostics.Process.Start("https://alexander0912ee.wixsite.com/systemworks-offical");
        }

        private void button5_Click(object sender, EventArgs e)
        {
            if (ErrorDiagnost.Text == "AN012455")
            {
                System.Diagnostics.Process.Start("https://alexander0912ee.wixsite.com/systemworks-offical/errors-an012455");
            }

            if (ErrorDiagnost.Text == "VALIDATIONSETINGSCONFORM")
            {
                System.Diagnostics.Process.Start("https://alexander0912ee.wixsite.com/systemworks-offical/copy-of-errors-an012455");
            }
        }

        private void button6_Click(object sender, EventArgs e)
        {
            if (ErrorDiagnost.Text == "AN012455")
            {
                MessageBox.Show("Enter a VALID command that can be usable in the project.", "Solution", MessageBoxButtons.OK, MessageBoxIcon.Exclamation);
            }
        }

        private void button7_Click(object sender, EventArgs e)
        {
            groupBox2.Visible = true;
            


        }

        private void button8_Click(object sender, EventArgs e)
        {
            groupBox2.Visible = false;
            


        }

        private void button9_Click(object sender, EventArgs e)
        {
            groupBox3.Visible = true;


            if (groupBox3.Visible == true)
            {
                return;
            }
        }

        private void button10_Click(object sender, EventArgs e)
        {
            groupBox3.Visible = false;
            
        }

        private void button11_Click(object sender, EventArgs e)
        {
            groupBox1.Visible = true;
            


        }

        private void panel2_Paint(object sender, PaintEventArgs e)
        {

        }

        private void button12_Click(object sender, EventArgs e)
        {
            System.Diagnostics.Process.Start(textboxlink.Text);

            if (button12.Text == "")
            {
                return;
            }
        }

        private void Form1_Load(object sender, EventArgs e)
        {
            // Set Tool Tips
            toolTip1.SetToolTip(Exit, "Exit the application");
            toolTip1.SetToolTip(Minimal, "Minimize or hide the application");
            toolTip1.SetToolTip(max, "Fullscreen the application (NOT SUPPORTED)");
            toolTip3.SetToolTip(NumberRight, "Your Input where you can code.");
            toolTip1.SetToolTip(Run, "Run your current input workspace");
            toolTip1.SetToolTip(Clear, "Clear up your input for nothing left in the input.");
            toolTip1.SetToolTip(Refresh, "Refresh to re-check status and restart from original text.");
            toolTip1.SetToolTip(button3, "Select A Coding Language to use");

            // Set Items
            comboBox1.SelectedItem = "Systemwork Project's V1.0.0 Language";

            // Files Saving
            new SaveFileDialog();

            System.Diagnostics.Process p = new System.Diagnostics.Process();
            p.StartInfo.FileName = "netsh.exe";
            p.StartInfo.Arguments = "wlan show interfaces";
            p.StartInfo.UseShellExecute = false;
            p.StartInfo.RedirectStandardOutput = true;
            p.Start();
        }

        private void button13_Click(object sender, EventArgs e)
        {
            groupBox4.Visible = true;
            


        }

        private void button14_Click(object sender, EventArgs e)
        {
            groupBox4.Visible = false;
            


        }

        private void groupBox3_Enter(object sender, EventArgs e)
        {

        }

        private void chart1_Click(object sender, EventArgs e)
        {

        }

        

        private void progressBar2_Click(object sender, EventArgs e)
        {

        }

        private void timer1_Tick(object sender, EventArgs e)
        {

        }

        private void textboxlink_TextChanged(object sender, EventArgs e)
        {

        }

        private void label5_Click(object sender, EventArgs e)
        {

        }

        private void checkBox1_CheckedChanged(object sender, EventArgs e)
        {
            if (checkBox1.Checked == true)
            {
                
                progressBar3.Visible = false;
            }

            if (checkBox1.Checked == false)
            {
                
                progressBar3.Visible = true;
            }
        }

        private void checkBox2_CheckedChanged(object sender, EventArgs e)
        {
            if (checkBox2.Checked == true)
            {
                NumberRight.Visible = false;
            }

            if (checkBox2.Checked == false)
            {
                NumberRight.Visible = true;
            }
        }

        private void groupBox2_Enter_1(object sender, EventArgs e)
        {

        }

        

        private void button15_Click(object sender, EventArgs e)
        {
            Form2 f2 = new Form2();
            f2.Show();
        }

        private void button16_Click(object sender, EventArgs e)
        {
            System.Diagnostics.Process.Start("https://alexander0912ee.wixsite.com/systemworks-offical");
        }

        private void button17_Click(object sender, EventArgs e)
        {
            Form3 f3 = new Form3();
            f3.Show();
        }

        private void ErrorDiagnost_TextChanged(object sender, EventArgs e)
        {
            if (ErrorDiagnost.Text == "VALIDATIONSETINGSCONFORM")
            {
                button6.Visible = false;
            }
            else
            {
                button6.Visible = true;
            }
        }

        private void button18_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void button19_Click(object sender, EventArgs e)
        {
            MinimizeBox = true;
        }


        private void Form1_Closing(object sender, FormClosingEventArgs e)
        {

        }

        private void panel1_Paint(object sender, PaintEventArgs e)
        {

        }

        private void Form1_HelpButtonClicked(object sender, CancelEventArgs e)
        {
            MessageBox.Show("Contact the owner for help", "Warning", MessageBoxButtons.OK, MessageBoxIcon.Warning);
        }

        

        private void comboBox1_SelectedIndexChanged(object sender, EventArgs e)
        {

        }

        private void button1_MouseHover(object sender, EventArgs e)
        {
            
        }

        private void button18_Click_1(object sender, EventArgs e)
        {
            Form4 f4 = new Form4();
            f4.Show();
        }

        private void textBox2_TextChanged(object sender, EventArgs e)
        {

        }

        private void button20_Click(object sender, EventArgs e)
        {
            System.Diagnostics.Process.Start("https://alexander0912ee.wixsite.com/systemworks-offical/private-idr-s");
        }

        private void textBox8_TextChanged(object sender, EventArgs e)
        {
            IDR.Text = IDR.Text.ToUpper();
        }

        private void Minimal_Click_1(object sender, EventArgs e)
        {
            WindowState = FormWindowState.Minimized;
        }

        private void button21_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void panel2_Paint_1(object sender, PaintEventArgs e)
        {

        }

        public const int WM_NCLBUTTONDOWN = 0xA1;
        public const int HTCAPTION = 0x2;
        [DllImport("User32.dll")]
        public static extern bool ReleaseCapture();
        [DllImport("User32.dll")]
        public static extern int SendMessage(IntPtr hWnd, int Msg, int wParam, int lParam);

        private void OnMouseDown(object sender, MouseEventArgs e)
        {
        if (e.Button == MouseButtons.Left)
        {
            ReleaseCapture();
            SendMessage(Handle, WM_NCLBUTTONDOWN, HTCAPTION, 0);
        }
        }

        private void button22_Click(object sender, EventArgs e)
        {
            WindowState = FormWindowState.Minimized;
        }

        private void button23_Click(object sender, EventArgs e)
        {
            Application.Exit();
        }

        private void max_Click(object sender, EventArgs e)
        {
            if (WindowState == FormWindowState.Normal)
            {
                WindowState = FormWindowState.Maximized;
            }
            else
            {
                WindowState = FormWindowState.Normal;
            }
        }

        private void button1_Click_1(object sender, EventArgs e)
        {
            StreamWriter Data = new StreamWriter("Systemworks ESO-Project/bin/Debug/DataText.txt");
            Data.Write("No data [[DOES THE USER DO ANY ACTIONS THAT MAY BE SAVED IN THE DATA?]]");
        }


        

        // 1 = false
        // 0 = true
        

        private void button19_Click_1(object sender, EventArgs e)
        {
            if (IDR.Text == "IM_SAID")
            {
                Form5 f5 = new Form5();
                f5.Visible = true;
            }
        }

        private void button1_Click_2(object sender, EventArgs e)
        {

        }

        private void documentMap1_Click(object sender, EventArgs e)
        {

        }

        private void button1_Click_3(object sender, EventArgs e)
        {
            System.Diagnostics.Process.Start("https://forms.gle/GM6JHAGHz9k4rjALA");
        }

        private void label8_Click(object sender, EventArgs e)
        {
            
        }

        private void button2_Click_1(object sender, EventArgs e)
        {
            Form4 f4 = new Form4();
            f4.Visible = true;
        }

        
        private void label8_Click_1(object sender, EventArgs e)
        {

        }

        private void checkBox3_CheckedChanged(object sender, EventArgs e)
        {
            if (checkBox3.Checked == true)
            {
                IDR.UseSystemPasswordChar = false;
            }
            else if (checkBox3.Checked == false) 
            {
                IDR.UseSystemPasswordChar = true;
            }
        }

        private void label4_Click(object sender, EventArgs e)
        {

        }

        

        private void comboBox1_SelectedIndexChanged_1(object sender, EventArgs e)
        {

        }

        private void button3_Click_1(object sender, EventArgs e)
        {
            if (comboBox1.SelectedItem == "Systemwork Project's V1.0.0 Language")
            {
                return;
            }

            else if (comboBox1.SelectedItem == "Systemwork Project's V1.0.0 Expert Language")
            {
                return;
            }

            else
            {
                MessageBox.Show("Coding Langauge Dosent exist", "Error");
                return;
            }
        }

        

        private void panel3_Paint(object sender, PaintEventArgs e)
        {

        }

        private void NumberRghtConsole_AfterSelect(object sender, TreeViewEventArgs e)
        {

        }

        private void treeView1_AfterSelect(object sender, TreeViewEventArgs e)
        {
            TreeNode node = treeView1.SelectedNode;
            if (node.Text == "Power Off")
            {
                if (MessageBox.Show("Are You Sure you want to Power Off?", "warning", MessageBoxButtons.YesNo, MessageBoxIcon.Warning) == DialogResult.Yes)
                {
                    Application.Exit();
                }
                else
                {
                    return;
                }

                if (node.Text == "Go to Site")
                {
                    System.Diagnostics.Process.Start("https://alexander0912ee.wixsite.com/systemworks-offical");
                }
            }
        }
    }
}
