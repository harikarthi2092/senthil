public void Test() 
{
   var session = new TestSession(); //start a browsing session
   var page = session.GetPage("Default.aspx"); //request a page
   var NameTextBox = (TextBox)page.FindControl("NameTextBox"); //find the textbox
   NameTextBox.Text = "John"; //enter the text
   page = session.ProcessPostback("SayButton"); //click the button*/
   var MessageLabel = (Label)page.FindControl("MessageLabel"); //finds the  label
   Assert.AreEqual("Hi John!", MessageLabel.Text, "Invalid text!"); //checks the  text
}
