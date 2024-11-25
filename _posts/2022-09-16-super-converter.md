---
layout: post
title: "Super Converter"
author: "Asher Pope"
date: 2022-09-16
tags: [dev, ios]
---

I started [Paul Hudson's 100 Days of SwiftUI](https://www.hackingwithswift.com/100/swiftui) course a few weeks back and will be periodically posting progress updates here and on [X (@asherpope)](https://twitter.com/asherpope).

After several days of painstaking work and lots of doing and undoing I have crafted the very advanced app Super Converter, which lets you convert inches to lightyears (among other measurements) if you so desire. You can view the source code below and [download the Swift Playground package here](https://drive.google.com/file/d/1O3Nia_zqZUOOhcsVJ0tp8Fg6zMC0XNrG/view?usp=sharing). 

```swift
import SwiftUI

struct ContentView: View {
    @State private var inputValue: Double = 0
    @State private var inputUnit: String = "Inches"
    @State private var outputUnit: String = "Centimeters"
    
    let units = ["Inches", "Feet", "Miles", "Centimeters", "Meters", "Kilometers", "Lightyears"]
    
    func stringToUnit(_ input: String) -> UnitLength {
        switch input {
        case "Inches": return .inches
        case "Feet": return .feet
        case "Miles": return .miles
        case "Centimeters": return .centimeters
        case "Meters": return .meters
        case "Kilometers": return .kilometers
        case "Lightyears": return .lightyears
        default: return .meters
        }
    }
    
    func convertUnit(inValue: Double, inUnit: String, outUnit: String) -> Double {
        let inputMeasurement = Measurement(value: inValue, unit: stringToUnit(inUnit))
        return inputMeasurement.converted(to: stringToUnit(outputUnit)).value
    }
    
    var body: some View {
        NavigationView {
            VStack {
                Form {
                    Section {
                        TextField("Input Value", value: $inputValue, format: .number)
                        Picker("Input Type", selection: $inputUnit) {
                            ForEach(units, id: \.self) { Text($0) }
                        }.pickerStyle(.menu)
                    } header: {
                        Text("input value")
                    }
                    
                    Section {
                        Text("\(convertUnit(inValue: inputValue, inUnit: inputUnit, outUnit: outputUnit).formatted())")
                        Picker("Output Type", selection: $outputUnit) {
                            ForEach(units, id: \.self) { Text($0) }
                        }.pickerStyle(.menu)
                    } header: {
                        Text("converted to")
                    }
                }.navigationTitle("Super Converter")
            }
        }
    }
}

```

*Copied from old Blogger account*