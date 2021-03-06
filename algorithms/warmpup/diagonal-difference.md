Given a square matrix of size N x N , calculate the absolute difference between the sums of its diagonals.

**Input Format**

The first line contains a single integer, N . The next N lines denote the matrix's rows, with each line containing space-separated integers describing the columns.

**Output Format**

Print the absolute difference between the two sums of the matrix's diagonals as a single integer.

**Sample Input**

    3
    11 2 4
    4 5 6
    10 8 -12

**Sample Output**

    15

**Explanation**

The primary diagonal is:

    11
        5
           -12

Sum across the primary diagonal: **11 + 5 - 12 = 4**

The secondary diagonal is:

           4
        5
    10

Sum across the secondary diagonal: `4 + 5 + 10 = 19`
Difference: `|4 - 19| = 15`

**Solution**
```javascript
    process.stdin.resume();
    process.stdin.setEncoding('ascii');

    var input_stdin = "";
    var input_stdin_array = "";
    var input_currentline = 0;

    process.stdin.on('data', function (data) {
        input_stdin += data;
    });

    process.stdin.on('end', function () {
        input_stdin_array = input_stdin.split("\n");
        main();    
    });

    function readLine() {
        return input_stdin_array[input_currentline++];
    }

    /////////////// ignore above this line ////////////////////

    function main() {
        var n = parseInt(readLine());
        var a = [];
        var primaryDiagonalSum = 0;
        var secondaryDiagonalSum = 0;
        for(a_i = 0; a_i < n; a_i++){
           a[a_i] = readLine().split(' ');
           a[a_i] = a[a_i].map(Number);
           primaryDiagonalSum += a[a_i][a_i];
           secondaryDiagonalSum += a[a_i][n-1-a_i];
        }
        console.log(Math.abs(primaryDiagonalSum - secondaryDiagonalSum));
    }
```
