Public Sub ClickingTheButton_DisplaysHiJohn()
    Dim session As New TestSession 'start a browsing session
    Dim page = session.GetPage("Default.aspx") 'request a page
    Dim NameTextBox As TextBox = page.FindControl("NameTextBox") 'find textbox
        NameTextBox.Text = "John" 'enter the text
        page = session.ProcessPostback("SayButton") 'click the button
    Dim MessageLabel As Label = page.FindControl("MessageLabel") 'finds the label
        Assert.AreEqual("Hi John!", MessageLabel.Text, "Invalid text") 'check text
End Sub
