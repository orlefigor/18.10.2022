# 18.10.2022
lekcja 18.10.2022


<!DOCTYPE html>
<html>
  <head>
    <title>cus</title>
  </head>
  <body>
    <script>
      /*
            ztab = [5, 4, 3, 2, 35, 43, 12, 6];
            ztab2 = [4, 3, 6, 32, 3, 5, 8, 67, 3];
            tab = [[3, 2, 4, 6, 8, 1, 3, 4]];
            console.log(tab);

            tab.push(ztab);

            tab.push(ztab2);
            for (i = 0; i < tab.length; i++) {
              for (j = 0; j < tab[i].length; j++) {
                console.log(tab[i][j]);
              }
            }
      */
      //--------------------------------------------------------------------------------

      let num1;
      let num2;
      let znak;
      const tab = [];
      let zm = true;
      let licz = 0;

      function GetData() {
        while (isNaN(num1)) {
          num1 = parseInt(prompt("podaj pierwszą liczbę:"));
        }
        while (isNaN(num2)) {
          num2 = parseInt(prompt("podaj drugą liczbę:"));
        }
        znak = prompt("podaj znak:");
      }

      function operation() {
        num1 = undefined;
        num2 = undefined;
        GetData();
        const tab2 = [];
        tab2.push(num1, num2, znak);
        tab.push(tab2);
      }
      function calc(i, tab) {
        switch (tab[i][2]) {
          case "+":
            return tab[i][0] + tab[i][1];
            break;
          case "-":
            return tab[i][0] - tab[i][1];
            break;
          case "/":
            return tab[i][0] / tab[i][1];
            break;
          case "*":
            return tab[i][0] * tab[i][1];
            break;
          default:
            return "zly operator";
            break;
        }
      }

      do {
        if (licz == 0) {
          operation();
        }
        if (licz != 0) {
          if (confirm("kolejne dzialanie?")) {
            operation();
          } else {
            zm = false;
            for (let i = 0; i < tab.length; i++) {
              document.write(calc(i, tab));
              document.write("<br>");
              console.log(tab[i]);
            }
          }
        }
        licz++;
      } while (zm);

      //-----------------------------------------------------------------
    </script>
  </body>
</html>
