```swift
import UIKit

class LogInViewController: UIViewController {
    let scrollView = UIScrollView()
    let contentView = UIView()
    let stackView = UIStackView()
    
    override func viewDidLoad() {
        super.viewDidLoad()
        
        view.backgroundColor = .white
        setupScrollView()
        setupLogoImage()
        setupStackView()
    }
    
    let logoImage: UIImageView = {
        let imageView = UIImageView(image: UIImage(named: "logo.png"))
        
        imageView.translatesAutoresizingMaskIntoConstraints = false
        return imageView
    }()
    
    let loginTextfield: UITextField = {
        
        let textField = UITextField()
        textField.placeholder = "Email and phone"
        textField.font = UIFont.systemFont(ofSize: 16)
        textField.keyboardType = UIKeyboardType.emailAddress
        textField.textColor = .black
        textField.autocapitalizationType = .none
        textField.layer.borderColor = UIColor.lightGray.cgColor
        textField.layer.borderWidth = 0.5
        textField.layer.cornerRadius = 10
        
        return textField
    }()
    
    let passwordTextfield: UITextField = {
        
        let textField = UITextField()
        textField.placeholder = "Password"
        textField.font = UIFont.systemFont(ofSize: 16)
        textField.keyboardType = UIKeyboardType.default
        textField.textColor = .black
        textField.autocapitalizationType = .none
        textField.layer.borderColor = UIColor.lightGray.cgColor
        textField.layer.borderWidth = 0.5
        textField.layer.cornerRadius = 10
        textField.isSecureTextEntry = true
        
        return textField
    }()
    
    
    
    func setupScrollView(){
        scrollView.translatesAutoresizingMaskIntoConstraints = false
        contentView.translatesAutoresizingMaskIntoConstraints = false
        view.addSubview(scrollView)
        scrollView.addSubview(contentView)
        
        NSLayoutConstraint.activate([
            
            scrollView.centerXAnchor.constraint(equalTo: view.centerXAnchor),
            scrollView.widthAnchor.constraint(equalTo: view.widthAnchor),
            scrollView.topAnchor.constraint(equalTo: view.topAnchor),
            scrollView.bottomAnchor.constraint(equalTo: view.bottomAnchor),
            
            contentView.centerXAnchor.constraint(equalTo: scrollView.centerXAnchor),
            contentView.widthAnchor.constraint(equalTo: scrollView.widthAnchor),
            contentView.topAnchor.constraint(equalTo: scrollView.topAnchor),
            contentView.bottomAnchor.constraint(equalTo: scrollView.bottomAnchor)
            
        ])
    }
    
    func setupLogoImage() {
        contentView.addSubview(logoImage)
        
        NSLayoutConstraint.activate([
            logoImage.centerXAnchor.constraint(equalTo: contentView.centerXAnchor),
            logoImage.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor, constant: 120),
            logoImage.widthAnchor.constraint(equalToConstant:100),
            logoImage.heightAnchor.constraint(equalToConstant: 100)
            
            
            
            ])
    }
    
    func setupStackView() {
        contentView.addSubview(stackView)
        
        stackView.axis = .vertical
        stackView.alignment = .center
        stackView.distribution = .fill
        stackView.addArrangedSubview(loginTextfield)
        stackView.addArrangedSubview(passwordTextfield)
        
        NSLayoutConstraint.activate([
            stackView.centerXAnchor.constraint(equalTo: contentView.centerXAnchor),
            stackView.topAnchor.constraint(equalTo: logoImage.bottomAnchor, constant: 120),
            stackView.leadingAnchor.constraint(equalTo: contentView.leadingAnchor, constant: 16),
            stackView.trailingAnchor.constraint(equalTo: contentView.trailingAnchor, constant: -16)
            
            
            
            
            ])
    }
    
}
```
