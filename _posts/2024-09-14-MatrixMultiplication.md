---
layout: post
title:  "Matrix Multiplication"
date:   2024-09-14 16:19:26 +0800
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
    <title>矩陣相乘計算器</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
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
        <h5>矩陣 A</h5>
        <label for="rowsA">Row數：</label>
        <input type="number" id="rowsA" value="2">
        <label for="colsA">Col數：</label>
        <input type="number" id="colsA" value="2">
        <button onclick="createMatrix('A')">生成矩陣 A</button>
        <div id="matrixA"></div>
    </div>
    <div class="matrix-container">
        <h5>矩陣 B</h5>
        <label for="rowsB">Row數：</label>
        <input type="number" id="rowsB" value="2">
        <label for="colsB">Col數：</label>
        <input type="number" id="colsB" value="2">
        <button onclick="createMatrix('B')">生成矩陣 B</button>
        <div id="matrixB"></div>
    </div>
    <button onclick="multiplyMatrices()">矩陣相乘</button>
    <h5>結果</h5>
    <div id="result"></div>
    <script>
        function createMatrix(matrixId) {
            let rows = document.getElementById(`rows${matrixId}`).value;
            let cols = document.getElementById(`cols${matrixId}`).value;
            let matrixDiv = document.getElementById(`matrix${matrixId}`);
            matrixDiv.innerHTML = '';
            let table = document.createElement('table');
            for (let i = 0; i < rows; i++) {
                let row = document.createElement('tr');
                for (let j = 0; j < cols; j++) {
                    let cell = document.createElement('td');
                    let input = document.createElement('input');
                    input.type = 'number';
                    input.id = `${matrixId}_${i}_${j}`;
                    cell.appendChild(input);
                    row.appendChild(cell);
                }
                table.appendChild(row);
            }
            matrixDiv.appendChild(table);
        }
        function getMatrixData(matrixId) {
            let rows = document.getElementById(`rows${matrixId}`).value;
            let cols = document.getElementById(`cols${matrixId}`).value;
            let matrix = [];
            for (let i = 0; i < rows; i++) {
                let row = [];
                for (let j = 0; j < cols; j++) {
                    let value = document.getElementById(`${matrixId}_${i}_${j}`).value;
                    row.push(parseInt(value));
                }
                matrix.push(row);
            }
            return matrix;
        }
        function multiplyMatrices() {
            let matrixA = getMatrixData('A');
            let matrixB = getMatrixData('B');
            let rowsA = matrixA.length;
            let colsA = matrixA[0].length;
            let rowsB = matrixB.length;
            let colsB = matrixB[0].length;
            if (colsA !== rowsB) {
                document.getElementById('result').innerText = '錯誤！矩陣 A 的列數必須等於矩陣 B 的行數。';
                return;
            }
            let result = [];
            for (let i = 0; i < rowsA; i++) {
                result[i] = [];
                for (let j = 0; j < colsB; j++) {
                    result[i][j] = 0;
                    for (let k = 0; k < colsA; k++) {
                        result[i][j] += matrixA[i][k] * matrixB[k][j];
                    }
                }
            }
            let tableHTML = '<table>';
            for (let i = 0; i < result.length; i++) {
                tableHTML += "<tr>";
                for (let j = 0; j < result[i].length; j++) {
                    tableHTML += `<td>　　${result[i][j]}　　</td>`;
                }
                tableHTML += "</tr>";
            }
            tableHTML += '</table>';
            let resultDiv = document.getElementById('result');
            resultDiv.innerHTML = tableHTML;
        }
    </script>
</body>
</html>
