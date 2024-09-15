---
layout: post
title:  "Equation Solver"
date:   2024-09-15 16:26:48 +0800
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
    <title>Equation Solver</title>
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
        <label for="size">有幾個未知數：</label>
        <input type="number" id="size" value="2" min="2" max="10"><br>
        <button onclick="createMatrix()">生成方程組</button>
        <div id="equationMatrix"></div>
    </div>
    <button onclick="solveEquations()">求解</button>
    <div id="result"></div>
    <script>
        function createMatrix() {
            let size = document.getElementById('size').value;
            let matrixDiv = document.getElementById('equationMatrix');
            matrixDiv.innerHTML = '';
            let table = document.createElement('table');
            for (let i = 0; i < size; i++) {
                let row = document.createElement('tr');
                for (let j = 0; j < size; j++) {
                    let cell = document.createElement('td');
                    let input = document.createElement('input');
                    input.type = 'number';
                    input.id = `matrix_${i}_${j}`;
                    input.placeholder = `a${i+1}${j+1}`;
                    cell.appendChild(input);
                    row.appendChild(cell);
                }
                let constCell = document.createElement('td');
                let constInput = document.createElement('input');
                constInput.type = 'number';
                constInput.id = `const_${i}`;
                constInput.placeholder = `b${i+1}`;
                constCell.appendChild(constInput);
                row.appendChild(constCell);
                table.appendChild(row);
            }
            matrixDiv.appendChild(table);
        }
        function getEquationData() {
            let size = document.getElementById('size').value;
            let matrix = [];
            let constants = [];
            for (let i = 0; i < size; i++) {
                let row = [];
                for (let j = 0; j < size; j++) {
                    let value = document.getElementById(`matrix_${i}_${j}`).value;
                    row.push(parseFloat(value));
                }
                matrix.push(row);
            }
            for (let i = 0; i < size; i++) {
                let value = document.getElementById(`const_${i}`).value;
                constants.push(parseFloat(value));
            }
            return {matrix, constants};
        }
        function solveEquations() {
            let { matrix, constants } = getEquationData();
            let size = matrix.length;
            for (let i = 0; i < size; i++) {
                matrix[i].push(constants[i]);
            }
            for (let i = 0; i < size; i++) {
                // 檢查主對角元素是否為0
                if (matrix[i][i] === 0) {
                    let swapped = false;
                    for (let k = i + 1; k < size; k++) {
                        if (matrix[k][i] !== 0) {
                            [matrix[i], matrix[k]] = [matrix[k], matrix[i]];
                            swapped = true;
                            break;
                        }
                    }
                    if (!swapped) {
                        document.getElementById('result').innerText = '錯誤！無法解此方程（主對角線元素為零且無法交換）。';
                        return;
                    }
                }
                let diagonal = matrix[i][i];
                for (let j = i; j < size + 1; j++) {
                    matrix[i][j] /= diagonal;
                }
                for (let k = 0; k < size; k++) {
                    if (k !== i) {
                        let factor = matrix[k][i];
                        for (let j = i; j < size + 1; j++) {
                            matrix[k][j] -= factor * matrix[i][j];
                        }
                    }
                }
            }
            let solutions = [];
            for (let i = 0; i < size; i++) {
                solutions.push(matrix[i][size]);
            }
            let resultDiv = document.getElementById('result');
            let resultHTML = '<h5>解：</h5><ul>';
            for (let i = 0; i < solutions.length; i++) {
                resultHTML += `<li>x${i+1} &nbsp;&nbsp;&nbsp; = &nbsp;&nbsp;&nbsp; ${solutions[i].toFixed(2)}</li>`;
            }
            resultHTML += '</ul>';
            resultDiv.innerHTML = resultHTML;
        }
    </script>
</body>
</html>
