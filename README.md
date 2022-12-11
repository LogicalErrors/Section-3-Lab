# Section-3-Lab
Section 3 Lab code

using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Security.Cryptography;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
//Ryan Bain
//ITD-1253-60498
//12-10-2022
namespace Sec3LabExam_Bain
{
    
    
    public partial class frmEncryption : Form

        

    {
        public frmEncryption()
        {
            InitializeComponent();
        }

        private void btnExit_Click(object sender, EventArgs e)
        {
            this.Close();
        }

        private void RadiobtnPlainText_CheckedChanged(object sender, EventArgs e)
        {
            try
            {
                lblResults.Text = Encoding.Unicode.GetString(Convert.FromBase64String(txtBoxInput.Text));
            }
            catch (FormatException)
            {
                lblResults.Text = "You can't Decrypt Plain Text.";
            }
        }

        private void RadiobtnCipherText_CheckedChanged(object sender, EventArgs e)
        {
            lblResults.Text = Convert.ToBase64String(Encoding.Unicode.GetBytes(txtBoxInput.Text));
            
            
        }

        private void btnDecode_Click(object sender, EventArgs e)
        {
            if(RadiobtnCipherText.Checked == true)
            {
                lblResults.Text = Convert.ToBase64String(Encoding.Unicode.GetBytes(txtBoxInput.Text));

            }

            else if(RadiobtnPlainText.Checked == true)
            {
                try
                {
                    lblResults.Text = Encoding.Unicode.GetString(Convert.FromBase64String(txtBoxInput.Text));
                }
                catch (FormatException)
                {
                    lblResults.Text = "You can't Decrypt Plain Text.";
                }
            }

        }

        private void btnReset_Click(object sender, EventArgs e)
        {
            lblResults.Text = "";
            txtBoxInput.Text = "";
            txtBoxInput.Focus();
        }

        private void lblResults_Click(object sender, EventArgs e)
        {

        }

        private void lblInfo_Click(object sender, EventArgs e)
        {

        }

        private void txtBoxInput_TextChanged(object sender, EventArgs e)
        {

        }
    }
}
