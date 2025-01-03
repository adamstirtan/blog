---
title: "Introducing NeuralNet.NET: A simple to use .NET library for Artificial Neural Networks"
seoTitle: "NeuralNet.NET: Easy .NET Neural Networks Library"
seoDescription: "NeuralNet.NET simplifies creating and training neural networks with .NET, featuring easy setup and customizable activation functions"
datePublished: Fri Jan 03 2025 13:17:22 GMT+0000 (Coordinated Universal Time)
cuid: cm5gs4z4q001d09jocw8lfvfm
slug: introducing-neuralnetnet-a-simple-to-use-net-library-for-artificial-neural-networks
tags: artificial-intelligence, neural-networks, activation-function, nuget, ann, artificial-neural-network

---

Artificial Neural Networks (ANNs) are a cornerstone of modern machine learning, enabling systems to learn from data and make intelligent decisions. However, implementing ANNs from scratch can be complex and time-consuming. That's where NeuralNet.Net comes in—a simple, easy-to-use .NET library designed to help you create and train neural networks with minimal effort.

# Getting Started

GitHub: [adamstirtan/](https://github.com/adamstirtan/NeuralNet.NET)[NeuralNet.NET](http://NeuralNet.NET)[: An extensible artificial neural network framework for .NET](https://github.com/adamstirtan/NeuralNet.NET)

NuGet: [NuGet Gallery |](https://www.nuget.org/packages/NeuralNet.Net/) [NeuralNet.Net](http://NeuralNet.Net) [1.0.0](https://www.nuget.org/packages/NeuralNet.Net/)

# Key Features

## Easy Setup

With NeuralNet.Net, you can quickly set up a neural network by specifying the number of layers and neurons. The library supports multiple activation functions, including Sigmoid, Tanh, and ReLU.

## Customizable Activation Functions

NeuralNet.Net allows you to use built-in activation functions or define your own. This flexibility ensures that you can tailor the network to your specific needs.

# Example Usage

Here's a quick example to demonstrate how easy it is to create, train, and use a neural network with NeuralNet.Net:

```csharp
using NeuralNet.Net;

class Program
{
    static void Main()
    {
        // Create a network with 2 input neurons, 2 hidden neurons, and 1 output neuron
        var nn = new ANN(new int[] { 2, 2, 1 }, 
            new ActivationFunctionType[] { ActivationFunctionType.Sigmoid, ActivationFunctionType.Sigmoid });
        
        // Training data (XOR-like)
        var trainingData = new List<(List<double>, List<double>)>
        {
            (new List<double> {0,0}, new List<double> {0}),
            (new List<double> {0,1}, new List<double> {1}),
            (new List<double> {1,0}, new List<double> {1}),
            (new List<double> {1,1}, new List<double> {0}),
        };

        nn.Train(trainingData, epochs: 1000, learningRate: 0.1);

        // Predict
        var result = nn.Predict(new List<double> {1,1});
        Console.WriteLine($"Output: {result[0]}");
    }
}
```