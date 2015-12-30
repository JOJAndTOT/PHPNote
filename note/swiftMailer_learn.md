##大纲
 * swiftMailerd的安装在[Composer_introduction.md](https://g.digi800.com/jywang1/work-notes-for-wxu/blob/master/note/composer_introduction.md)中提过
 * swiftMailer自动加载
 * swiftMailer创建一个消息
 * swiftMailer发送一个消息
 
##加载
  如果安装了Composer则会自动加载，如果没有安装Composer则使用
```
require_once '/path/to/swift-mailer/lib/swift_required.php';
```
##创建消息

>// Create the message
>$message = Swift_Message::newInstance()
>
>// Give the message a subject
>  ->setSubject('Your subject')

>  // Set the From address with an associative array
>  ->setFrom(array('john@doe.com' => 'John Doe'))

> // Set the To addresses with an associative array
>  ->setTo(array('receiver@domain.org', >'other@domain.org' => 'A name'))

>  // Give it a body
>  ->setBody('Here is the message itself')

>  // And optionally an alternative body
>  ->addPart('<q>Here is the message itself</q>', 'text/html')

>  // Optionally add any attachments
>  ->attach(Swift_Attachment::fromPath('my-document.pdf'));

##发送消息

  需要创建Transport，自己提供Swift_SmtpTransport, Swift_SendmailTransport, Swift_MailTransport。

  其中Transport的实现方式及相关描述请[点击](http://swiftmailer.org/docs/sending.html)

  发送过程：

>$mailer = Swift_Mailer::newInstance($transport);
>$result = $mailer->send($message);


