import 'package:flutter/material.dart';
import 'package:flutter/cupertino.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatefulWidget {
  @override
  _MyAppState createState() => _MyAppState();
}

class _MyAppState extends State<MyApp> {
  String output = '0';
  String _output = '0';
  double num1 = 0.0;
  double num2 = 0.0;
  String operand = '';
  operation(String btntext) {
    if (btntext == "C") {
      num1 = 0.0;
      num2 = 0.0;
      _output = '0';
      operand = "";
    } else if (btntext == '=') {
      num2 = double.parse(output);
      if (operand == '+') {
        _output = (num1 + num2).toString();
      } else if (operand == '-') {
        _output = (num1 - num2).toString();
      } else if (operand == '*') {
        _output = (num1 * num2).toString();
      } else {
        _output = (num1 / num2).toString();
      }
      num1 = 0.0;
      num2 = 0.0;
      operand = "";
    } else {
      _output = _output + btntext;
    }
    setState(() {
      output = double.parse(output).toStringAsFixed(2);
    });
  }

  Widget button(String btntext) {
    return Expanded(
      child: RawMaterialButton(
        shape: Border.all(color: Colors.black, width: 2),
        onPressed: () {
          operation(btntext);
        },
        splashColor: Colors.black,
        fillColor: Colors.grey,
        padding: EdgeInsets.all(28),
        child: Container(
          child: Text(
            "$btntext",
            style: TextStyle(
                fontSize: 20,
                fontWeight: FontWeight.w600,
                color: Colors.black87),
          ),
        ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
        debugShowCheckedModeBanner: false,
        home: Scaffold(
          appBar: AppBar(
            title: Text("Calculator"),
            backgroundColor: Colors.black87,
          ),
          body: Container(
              child: Column(
            mainAxisAlignment: MainAxisAlignment.end,
            children: [
              Expanded(
                child: Container(
                  alignment: Alignment.bottomRight,
                  padding: EdgeInsets.all(20),
                  child: Text(
                    "$output",
                    style: TextStyle(
                      color: Colors.black,
                      fontSize: 40,
                      backgroundColor: Colors.white,
                    ),
                  ),
                ),
              ),
              Row(
                children: [
                  button('9'),
                  button('8'),
                  button('7'),
                  button('6'),
                ],
              ),
              Row(
                children: [
                  button('5'),
                  button('4'),
                  button('3'),
                  button('2'),
                ],
              ),
              Row(
                children: [
                  button('1'),
                  button('0'),
                  button('+'),
                  button('-'),
                ],
              ),
              Row(
                children: [
                  button("C"),
                  button('='),
                  button("/"),
                  button("*"),
                ],
              ),
            ],
          )),
        ));
  }
}
