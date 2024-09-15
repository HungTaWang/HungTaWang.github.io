---
layout: post
title:  "Matrix Inverse"
date:   2024-09-15 11:35:17 +0800
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
    <title>反矩陣計算器</title>
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
				width: 125px;
				height: 55px;
				margin: 20px;
				font-weight: bold;
			}
    </style>
</head>
<body>
    <h4>反矩陣計算器</h4>
    <div class="matrix-container">
        <h5>輸入矩陣</h5>
        <label for="size">矩陣大小：</label>
        <input type="number" id="size" value="2" min="2" max="10">
        <button onclick="createMatrix()">生成矩陣</button>
        <div id="matrix"></div>
    </div>
    <button onclick="invertMatrix()">求反矩陣</button>
    <h5>結果</h5>
    <div id="result"></div>
    <script>
        function createMatrix() {
            let size = document.getElementById('size').value;
            let matrixDiv = document.getElementById('matrix');
            matrixDiv.innerHTML = '';
            let table = document.createElement('table');
            for (let i = 0; i < size; i++) {
                let row = document.createElement('tr');
                for (let j = 0; j < size; j++) {
                    let cell = document.createElement('td');
                    let input = document.createElement('input');
                    input.type = 'number';
                    input.id = `matrix_${i}_${j}`;
                    cell.appendChild(input);
                    row.appendChild(cell);
                }
                table.appendChild(row);
            }
            matrixDiv.appendChild(table);
        }
        function getMatrixData() {
            let size = document.getElementById('size').value;
            let matrix = [];
            for (let i = 0; i < size; i++) {
                let row = [];
                for (let j = 0; j < size; j++) {
                    let value = document.getElementById(`matrix_${i}_${j}`).value;
                    row.push(parseFloat(value));
                }
                matrix.push(row);
            }
            return matrix;
        }
        function invertMatrix() {
            let matrix = getMatrixData();
            let size = matrix.length;
            let identityMatrix = [];
            for (let i = 0; i < size; i++) {
                identityMatrix[i] = [];
                for (let j = 0; j < size; j++) {
                    identityMatrix[i][j] = i === j ? 1 : 0;
                }
            }
            for (let i = 0; i < size; i++) {
                let pivot = matrix[i][i];
                if (pivot === 0) {
                    document.getElementById('result').innerText = '錯誤！無法計算反矩陣（可能是奇異矩陣）。';
                    return;
                }
                for (let j = 0; j < size; j++) {
                    matrix[i][j] /= pivot;
                    identityMatrix[i][j] /= pivot;
                }
                for (let k = 0; k < size; k++) {
                    if (k !== i) {
                        let factor = matrix[k][i];
                        for (let j = 0; j < size; j++) {
                            matrix[k][j] -= factor * matrix[i][j];
                            identityMatrix[k][j] -= factor * identityMatrix[i][j];
                        }
                    }
                }
            }
            let tableHTML = '<table>';
            for (let i = 0; i < size; i++) {
                tableHTML += "<tr>";
                for (let j = 0; j < size; j++) {
                    tableHTML += `<td>　　${identityMatrix[i][j].toFixed(2)}　　</td>`;
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
