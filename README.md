# noviembre-diciembre

      static boolean esLetraMayuscula(char caracter) {
          return 'A' <= caracter && caracter <= 'Z' && caracter != 'Ñ';
      }
      
      static boolean esDigito(char caracter) {
          return '0' <= caracter && caracter <= '9';
      }
      
      static boolean tieneFormatoNIF(char[] array) {
          if (array.length != 9) return false;
          for (int i = 0; i < 8; i++) {
              if (!esDigito(array[i])) return false;
          }
          return esLetraMayuscula(array[8]);
      }
      
      // Ejemplo de uso:
      public static void main(String[] args) {
          System.out.println(tieneFormatoNIF(new char[]{'0','3','4','4','5','0','8','5','Z'})); // true
          System.out.println(tieneFormatoNIF(new char[]{'0','3','4','?','5','0','8','5','Z'})); // false
          System.out.println(tieneFormatoNIF(new char[]{'0','3','4','9','5'})); // false
      }

          static int aDigito(char caracter) {
        return caracter - '0';
    }

    static int aNum(char[] array) {
        int numero = 0;
        for (int i = 0; i < 8; i++) {
            numero = numero * 10 + aDigito(array[i]);
        }
        return numero;
    }
    
    // Ejemplo de uso:
    public static void main(String[] args) {
        System.out.println(aNum(new char[]{'0','8','9','2','8','8','6','7','Z'})); // 8928867
        System.out.println(aNum(new char[]{'0','0','0','0','0','0','2','4','R'})); // 24
    }

          static int busqueda(int[] array, int objetivo) {
          int inicio = 0, fin = array.length - 1, resultado = -1;
          while (inicio <= fin) {
              int medio = (inicio + fin) / 2;
              if (array[medio] >= objetivo) {
                  resultado = medio; // Posible índice del primer elemento igual o mayor
                  fin = medio - 1;   // Continúa buscando a la izquierda
              } else {
                  inicio = medio + 1;
              }
          }
          return resultado;
      }
      
      // Ejemplo de uso:
      public static void main(String[] args) {
          System.out.println(busqueda(new int[]{1, 2, 4, 5, 6}, 5)); // 3
          System.out.println(busqueda(new int[]{1, 2, 4, 5, 6}, 3)); // 2
      }

            static String traducirDireccion(char direccion) {
          switch (direccion) {
              case 'N': return "Norte";
              case 'S': return "Sur";
              case 'E': return "Este";
              case 'W': return "Oeste";
              default: return "DIRECCIÓN ERRÓNEA";
          }
      }
      
      // Ejemplo de uso:
      public static void main(String[] args) {
          System.out.println(traducirDireccion('W')); // Oeste
          System.out.println(traducirDireccion('N')); // Norte
          System.out.println(traducirDireccion('X')); // DIRECCIÓN ERRÓNEA
      }



