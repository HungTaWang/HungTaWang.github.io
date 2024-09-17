---
layout: post
title:  "Polynomial Addition"
date:   2024-09-17 22:03:19 +0800
categories: Tools
tags: National_Taiwan_University
comments: 1
published: true
---

> Have fun here!

<html lang="zh-Hant">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Polynomial Addition</title>
    <style>
        .matrix-container {
            margin-bottom: 20px;
        }
        input[type="number"] {
            width: 50px;
            text-align: center;
        }
        table {
            margin-bottom: 20px;
        }
        td {
            padding: 5px;
        }
        button{
				border-radius: 50px;
				background-color: #fff6a8;
				font-size: 20px;
				border-style: outset; 
				width: 180px;
				height: 55px;
				margin: 20px;
				font-weight: bold;
			}
    </style>
</head>
<body>
    <div class="matrix-container">
        <label for="degree1">多項式 A 的最高次：</label>
        <input type="number" id="degree1" value="2" min="1" max="10">
        <button onclick="createPolyInput(1)">生成多項式 A</button>
        <div id="poly1Container"></div>        
        <label for="degree2">多項式 B 的最高次：</label>
        <input type="number" id="degree2" value="2" min="1" max="10">
        <button onclick="createPolyInput(2)">生成多項式 B</button>
        <div id="poly2Container"></div>
    </div>
    <button onclick="addPolynomials()">多項式相加</button>
    <div id="result"></div>
    <script>
        function createPolyInput(polyNum) {
            let degree = document.getElementById(`degree${polyNum}`).value;
            let polyDiv = document.getElementById(`poly${polyNum}Container`);
            polyDiv.innerHTML = '';
            let table = document.createElement('table');
            let row = document.createElement('tr');
            for (let i = degree; i >= 0; i--) {
                let cell = document.createElement('td');
                let input = document.createElement('input');
                input.type = 'number';
                input.id = `poly${polyNum}_coef_${i}`;
                input.placeholder = `x^${degree - i}`;
                cell.appendChild(input);
                row.appendChild(cell);
            }
            table.appendChild(row);
            polyDiv.appendChild(table);
        }
        function getPolynomialCoefficients(polyNum) {
            let degree = document.getElementById(`degree${polyNum}`).value;
            let coefficients = [];
            for (let i = degree; i >= 0; i--) {
                let value = parseFloat(document.getElementById(`poly${polyNum}_coef_${i}`).value);
                coefficients.push(isNaN(value) ? 0 : value);
            }
            return coefficients;
        }
        function addPolynomials() {
            let poly1 = getPolynomialCoefficients(1);
            let poly2 = getPolynomialCoefficients(2);
            let maxDegree = Math.max(poly1.length, poly2.length);
            let result = new Array(maxDegree).fill(0);
            for (let i = 0; i < maxDegree; i++) {
                let coef1 = i < poly1.length ? poly1[i] : 0;
                let coef2 = i < poly2.length ? poly2[i] : 0;
                result[i] = coef1 + coef2;
            }
            displayResult(result);
        }
        function displayResult(result) {
            let resultDiv = document.getElementById('result');
            let resultHTML = '<h5>結果：</h5><p>';
            for (let i = result.length - 1; i >= 0; i--) {
                let coef = result[i].toFixed(2);
                if (coef != 0) {
                    resultHTML += `${coef}x<sup>${i}</sup> `;
                    if (i > 0) {
                        resultHTML += '+ ';
                    }
                }
                if (coef == 0 && i == 0){
                    resultHTML += '0';
                }
            }
            resultHTML += '</p>';
            resultDiv.innerHTML = resultHTML;
        }
    </script>

</body>
</html>
