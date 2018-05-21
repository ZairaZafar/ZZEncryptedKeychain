# ZZEncryptedKeychain
A wrapper introduced to ease encryption/decryption without the knowledge of Security in iOS. It allows easy encrypted storage to keychain, and keychain implementation is made easy with just a caller method, your data is securely stored in keychain.

Follow the demo app, it contains a simple note keeping application that requires a password and a username.

Use method EncryptToKeychain and DecryptToKeychain to save data into keychains securely.
Also a sample EncryptToDefaults and DecryptFromDefaults shows an implementation how the encryption wrapper is general purpose encryption and can also be applied to user defaults.
Similiar implementation can be created by user for Core Data just call following methods:

<pre>
let data = self.encrypt(data: data, key: KeychainConfiguration.key)

let stringData = self.convertToBase64String(data: data)
</pre>
StringData now can be saved to CoreData

For decryption fetch from CoreData and Follow:
<pre>
 let data = self.convertToDataFromBase64String(string: fetchedData)
 let actualData = self.decryptData(data: data, key: KeychainConfiguration.key)!
 </pre>
 or
 <pre>
 return self.decryptData(data: data, key: KeychainConfiguration.key)!
</pre>
