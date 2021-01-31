/ *
* HomeInventory.java
*/
package homeinventory;
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
public class HomeInventory extends JFrame
{
public static void main(String args[])
{
// create frame
new HomeInventory().show();
}
public HomeInventory()
{
// frame constructor
setTitle("Home Inventory Manager");
setResizable(false);
addWindowListener(new WindowAdapter()
{
public void windowClosing(WindowEvent evt)
Suven Internship
{
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

// Toolbar
JToolBar inventoryToolBar = new JToolBar();
JButton newButton = new JButton(new ImageIcon("new.gif"));
JButton deleteButton = new JButton(new ImageIcon("delete.gif"));
JButton saveButton = new JButton(new ImageIcon("save.gif"));
JButton previousButton = new JButton(new ImageIcon("previous.gif"));
JButton nextButton = new JButton(new ImageIcon("next.gif"));
JButton printButton = new JButton(new ImageIcon("print.gif"));
JButton exitButton = new JButton();

inventoryToolBar.setFloatable(false);
inventoryToolBar.setBackground(Color.BLUE);
inventoryToolBar.setOrientation(SwingConstants.VERTICAL);
gridConstraints = new GridBagConstraints();
gridConstraints.gridx = 0;
gridConstraints.gridy = 0;
Suven Internship
gridConstraints.gridheight = 8;
gridConstraints.fill = GridBagConstraints.VERTICAL;
getContentPane().add(inventoryToolBar, gridConstraints);
inventoryToolBar.addSeparator();
Dimension bSize = new Dimension(70, 50);
newButton.setText("New");
sizeButton(newButton, bSize);
newButton.setToolTipText("Add New Item");
newButton.setHorizontalTextPosition(SwingConstants.CENTER);
newButton.setVerticalTextPosition(SwingConstants.BOTTOM);
inventoryToolBar.add(newButton);
newButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
newButtonActionPerformed(e);
}
});
deleteButton.setText("Delete");
sizeButton(deleteButton, bSize);
deleteButton.setToolTipText("Delete Current Item");
deleteButton.setHorizontalTextPosition(SwingConstants.CENTER);
deleteButton.setVerticalTextPosition(SwingConstants.BOTTOM);
inventoryToolBar.add(deleteButton);
deleteButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
deleteButtonActionPerformed(e);
}
});
saveButton.setText("Save");
sizeButton(saveButton, bSize);
Suven Internship
saveButton.setToolTipText("Save Current Item");
saveButton.setHorizontalTextPosition(SwingConstants.CENTER);
saveButton.setVerticalTextPosition(SwingConstants.BOTTOM);
inventoryToolBar.add(saveButton);
saveButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
saveButtonActionPerformed(e);
}
});
inventoryToolBar.addSeparator();
previousButton.setText("Previous");
sizeButton(previousButton, bSize);
previousButton.setToolTipText("Display Previous Item");
previousButton.setHorizontalTextPosition(SwingConstants.CENTER);
previousButton.setVerticalTextPosition(SwingConstants.BOTTOM);
inventoryToolBar.add(previousButton);
previousButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
previousButtonActionPerformed(e);
}
});
nextButton.setText("Next");
sizeButton(nextButton, bSize);
nextButton.setToolTipText("Display Next Item");
nextButton.setHorizontalTextPosition(SwingConstants.CENTER);
nextButton.setVerticalTextPosition(SwingConstants.BOTTOM);
inventoryToolBar.add(nextButton);
nextButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
Suven Internship
{
nextButtonActionPerformed(e);
}
});
inventoryToolBar.addSeparator();
printButton.setText("Print");
sizeButton(printButton, bSize);
printButton.setToolTipText("Print Inventory List");
printButton.setHorizontalTextPosition(SwingConstants.CENTER);
printButton.setVerticalTextPosition(SwingConstants.BOTTOM);
inventoryToolBar.add(printButton);
printButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
printButtonActionPerformed(e);
}
});
exitButton.setText("Exit");
sizeButton(exitButton, bSize);
exitButton.setToolTipText("Exit Program");
inventoryToolBar.add(exitButton);
exitButton.addActionListener(new ActionListener()
{
public void actionPerformed(ActionEvent e)
{
exitButtonActionPerformed(e);
}
});