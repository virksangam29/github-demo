# github-demo
echo "# github-demo" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/virksangam29/github-demo.git
git push -u origin main
import javax.swing.*;
import java.awt.event.*;

public class LoginDemo implements ActionListener {
    private JFrame frame;
    private JPanel panel;
    private JTextField emailField;
    private JPasswordField passwordField;
    private JButton loginButton;

    public LoginDemo() {
        frame = new JFrame("Login Page");
        panel = new JPanel();
        emailField = new JTextField(20);
        passwordField = new JPasswordField(20);
        loginButton = new JButton("Login");

        loginButton.addActionListener(this);

        panel.add(new JLabel("Email:"));
        panel.add(emailField);
        panel.add(new JLabel("Password:"));
        panel.add(passwordField);
        panel.add(loginButton);

        frame.add(panel);
        frame.setSize(300, 200);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setVisible(true);
    }

    public void actionPerformed(ActionEvent e) {
        String email = emailField.getText();
        String password = new String(passwordField.getPassword());

        // Perform your authentication logic here
        if (email.equals("user@example.com") && password.equals("password")) {
            JOptionPane.showMessageDialog(frame, "Login Successful!");
        } else {
            JOptionPane.showMessageDialog(frame, "Incorrect Email or Password", "Error", JOptionPane.ERROR_MESSAGE);
        }
    }

    public static void main(String[] args) {
        SwingUtilities.invokeLater(new Runnable() {
            public void run() {
                new LoginDemo();
            }
        });
    }
}
