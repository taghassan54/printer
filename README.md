# printer

```
  all_printer:
    git:
      url: https://github.com/taghassan54/printer.git
      ref: main # branch name
```
## import 

```
import 'package:all_printer/all_printer.dart';
```
## use 
```

 final _allPrinterPlugin = AllPrinter();
 
 Dio dio =Dio();
 
```
 #
```
 for image print use this :
 
 String path = await _allPrinterPlugin.getDownloadPath("unique name");
 
    bool isDone = await _allPrinterPlugin.download(
        dio,
        "https://raw.githubusercontent.com/taghassan54/printer/main/printing.bmp",
        path);
        
```
  #      
 ```
        
        dynamic  invoice = {
          "0": "The Quick Brown fox jumped over The Lazy Dog",
          "1": "Date:2022-01-30 10:25:35",
          "2": "Name: Altkamul Printer Test",
          "3": "Merchent ID: 10005000",
          "4": "Terminal ID: 667766776",
          "5": "Transaction ID: 10000001",
          "6": "Voucher No: 22-003111",
          "7": "Car No: 1001k",
          "8": "Customer No: 971512345678",
          "9": "******************************",
          "10": "Tax Invoice",
          "11": "******************************",
          "12": "Title: Exterir Wash Small Car",
          "13": "service: Wash",
          "14": "price: 35.00",
          "15": "qty: 2",
          "16": "Total Qty: 2",
          "17": "Total Befor Vat: 70.00 AED",
          "18": "Vat: @5%: 11.00 AED",
          "19": "-------------------------------",
          "20": "Total: 71.00 AED",
          "21": "******************************",
          "22": "City: Dubai UAE Call Us : 05123456789",
          "23": "-------------------------------",
          "24": "Thanks you for try our Flutter base POS"
        };
        
         invoice['logoPath'] = path;
         
         await _allPrinterPlugin.print(invoice: invoice) ?? '';
         
         await _allPrinterPlugin.printSingleLine(line: "this normal text !") ??
            '';
            
         _allPrinterPlugin.printQrCode(qrData: "data");
               
               
         await _allPrinterPlugin.printImage(imagePath: path) ?? '';
                 
          _allPrinterPlugin.printReyFinish();
        
```
