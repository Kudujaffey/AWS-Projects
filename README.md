# AWS-Projects
<!DOCTYPE html>
<html>
<head>
    <title>Addition Problem Solver</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 20px;
        }
        h1 {
            color: #333;
        }
    </style>
</head>
<body>
    <h1>Addition Problem Solver</h1>
    <p>Enter an addition problem:</p>
    <input type="text" id="problem" placeholder="e.g., 2 + 3">
    <button onclick="solve()">Solve</button>
    <p id="result"></p>

    <script>
        function solve() {
            const problemInput = document.getElementById("problem");
            const resultElement = document.getElementById("result");
            
            try {
                const problem = problemInput.value;
                const parts = problem.split('+');
                if (parts.length !== 2) {
                    throw "Invalid format";
                }
                
                const num1 = parseFloat(parts[0]);
                const num2 = parseFloat(parts[1]);
                
                if (isNaN(num1) || isNaN(num2)) {
                    throw "Invalid numbers";
                }
                
                const sum = num1 + num2;
                resultElement.textContent = `Result: ${sum}`;
            } catch (error) {
                resultElement.textContent = `Error: ${error}`;
            }
        }
    </script>
</body>
</html>
