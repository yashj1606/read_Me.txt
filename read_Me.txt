/ *
* LoanAssistant.java
*/
package loanassistant;
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
public class LoanAssistant extends JFrame
{
public static void main(String args[])
{
// create frame
new LoanAssistant().show();
}
public LoanAssistant()
{
// frame constructor
setTitle("Loan Assistant");
setResizable(false);
addWindowListener(new WindowAdapter()
{
public void windowClosing(WindowEvent evt)
{
Suven Internship
exitForm(evt);
}
});
getContentPane().setLayout(new GridBagLayout());
GridBagConstraints gridConstraints;
pack();
Dimension screenSize =
Toolkit.getDefaultToolkit().getScreenSize();
setBounds((int) (0.5 * (screenSize.width - getWidth())), (int) (0.5 * (screenSize.height
- getHeight())), getWidth(), getHeight());
}
private void exitForm(WindowEvent evt)
{
System.exit(0);
}
}

JLabel balanceLabel = new JLabel();
JTextField balanceTextField = new JTextField();
JLabel interestLabel = new JLabel();
JTextField interestTextField = new JTextField();
JLabel monthsLabel = new JLabel();
JTextField monthsTextField = new JTextField();
Suven Internship
JLabel paymentLabel = new JLabel();
JTextField paymentTextField = new JTextField();
Note the labels and text fields all use the same font. Let’s create a Font object to use in each:
Font myFont = new Font("Arial", Font.PLAIN, 16);
Now, the controls are added to the frame using (recall code goes in frame constructor):
balanceLabel.setText("Loan Balance");
balanceLabel.setFont(myFont);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 0;
gridConstraints.gridy = 0;
gridConstraints.anchor = GridBagConstraints.WEST;
gridConstraints.insets = new Insets(10, 10, 0, 0);
getContentPane().add(balanceLabel, gridConstraints);
balanceTextField.setPreferredSize(new Dimension(100, 25));
balanceTextField.setHorizontalAlignment(SwingConstants.RIGHT);
balanceTextField.setFont(myFont);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 1;
gridConstraints.gridy = 0;
gridConstraints.insets = new Insets(10, 10, 0, 10);
getContentPane().add(balanceTextField, gridConstraints);
interestLabel.setText("Interest Rate");
interestLabel.setFont(myFont);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 0;
gridConstraints.gridy = 1;
gridConstraints.anchor = GridBagConstraints.WEST;
gridConstraints.insets = new Insets(10, 10, 0, 0);
getContentPane().add(interestLabel, gridConstraints);
interestTextField.setPreferredSize(new Dimension(100, 25));
interestTextField.setHorizontalAlignment(SwingConstants.RIGHT);

interestTextField.setFont(myFont);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 1;
gridConstraints.gridy = 1;
gridConstraints.insets = new Insets(10, 10, 0, 10);
getContentPane().add(interestTextField, gridConstraints);
monthsLabel.setText("Number of Payments");
monthsLabel.setFont(myFont);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 0;
gridConstraints.gridy = 2;
gridConstraints.anchor = GridBagConstraints.WEST;
gridConstraints.insets = new Insets(10, 10, 0, 0);
getContentPane().add(monthsLabel, gridConstraints);
monthsTextField.setPreferredSize(new Dimension(100, 25));
monthsTextField.setHorizontalAlignment(SwingConstants.RIGHT);
monthsTextField.setFont(myFont);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 1;
gridConstraints.gridy = 2;
gridConstraints.insets = new Insets(10, 10, 0, 10);
getContentPane().add(monthsTextField, gridConstraints);
paymentLabel.setText("Monthly Payment");
paymentLabel.setFont(myFont);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 0;
gridConstraints.gridy = 3;
gridConstraints.anchor = GridBagConstraints.WEST;
gridConstraints.insets = new Insets(10, 10, 0, 0);
getContentPane().add(paymentLabel, gridConstraints);
paymentTextField.setPreferredSize(new Dimension(100, 25));
paymentTextField.setHorizontalAlignment(SwingConstants.RIGHT);
paymentTextField.setFont(myFont);
Suven Internship
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 1;
gridConstraints.gridy = 3;
gridConstraints.insets = new Insets(10, 10, 0, 10);
getContentPane().add(paymentTextField, gridConstraints);

JButton computeButton = new JButton();
JButton newLoanButton = new JButton();

computeButton.setText("Compute Monthly Payment");
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 0;
gridConstraints.gridy = 4;
gridConstraints.gridwidth = 2;
gridConstraints.insets = new Insets(10, 0, 0, 0);
getContentPane().add(computeButton, gridConstraints);
computeButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
computeButtonActionPerformed(e);
}
});
newLoanButton.setText("New Loan Analysis");
newLoanButton.setEnabled(false);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 0;
gridConstraints.gridy = 5;
gridConstraints.gridwidth = 2;
gridConstraints.insets = new Insets(10, 0, 10, 0);
getContentPane().add(newLoanButton, gridConstraints);
newLoanButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
newLoanButtonActionPerformed(e);
}
});
This code also adds listeners for each button. Add these empty methods:
private void computeButtonActionPerformed(ActionEvent e)
{
}

private void newLoanButtonActionPerformed(ActionEvent e)
{
}