# VisualCode

## Crear un nou entorn

Terminal → Nuevo terminal → dotnet new console

dotnet new console —use—program—main 

## Tipus d’operacions

 =  Es asignació

+ Suma

- Resta

* Multiplicació

/ Divisó

% Resto

! Negació

< Més petit

> Més gran

≤ Més petit o igual

≥ Més gran o igual

|| OR

== Igualdad

++ Increment +1

Ex. Valor1 ++, Valor2 —

&& AND

! = Desigual

— Desincrement -1

---

### Typecasting

S’utiliza per especifica que el resultat d’una acció ha de ser d’un tipus de variable en concret.

Ex. (double) a/b; aixó implica que el resultat d’aquesta divisió serà decimal tot i que a o b siguin int.

Ex. (char) a; aixó implica que es mostrarà la lletra o el caràcter al cual correspon en la taula ASCII

Ex. (int) a; aixó implica que si a és una variable tipus char, es mostrarà el codi, numero,  ASCII de la lletra.

# Comandes C#

```csharp
Console.Writeline("");
```

> Escriure alguna cosa per pantalla
> 

> Establir una variable, pot ser entera (int), o decimal (double), o un caràcter (char), o un conjunt de caràcters com un nom (string). Bool pot ser true o false.
> 

[Tipus Bàsics C#.pdf](VisualCode%2018e87ea7b9064e22acdc5f05da88f99c/Tipus_Bsics_C.pdf)

```csharp
int valor1; 
double valor2;
char valor3;
string valor4
bool valor5;
```

```csharp
valor1 = Convert.ToInt32(Console.Readline());
valor2 = Console.Readkey().Keychar;
```

- ReadKey
    
    Si a Readkey(True) la consola llegeix direcament el valor introduit i no el mostra a pantalla
    

> Llegir un valor introduit per l’usuari.
> 

> Constants
> 

```csharp
const int valor1 = x;
const double valor2 = y;
```

---

> Condicionals
> 

```csharp
if () {

}
else if () {

}
else {

}
```

> Switch
> 

```csharp
switch (valor1) {
		case 1:
				
		break;

		case 2:

		break;

		default:

		break;
}
```

### Estrutures de repetició (Iteracions)

for:  comptar un recompte de cuantes vegades hem realitzat una tasca.

while: fer alguna cosa mentres es compleix una condició.

```csharp
while () {

}
```

```csharp
do {

}
while () {

}
```

```csharp
for (i=0; i < o > N; i++) {

}
```

# Seqüencies

lletra + enter + lletra + enter …

```csharp
c = Convert.ToChar(Console.ReadLine());
c = char.Parse(Console.ReadLine());
```

Torna el codi ASCII del caracter

```csharp
c = (char)Console.Read();
```

Agafa un caracter, no cal enter

```csharp
c = Console.ReadKey().KeyChar;
```

## Metodes

És una manera de cridar a un mini programa que fa alguna cosa en concret.

Hi ha dos parts principals en aquest tipus de programes: 

- El main: és el programa principal del cual es criden als metodes.
- Els metodes: son els mini programes que fa alguna cosa.

Estructura bàsica de un programa: 

```csharp
namespace nomdelprograma;
class Program
{
    static void Main(string[] args){

    }
    static bool metodes1(int n){
					
    }
}
```

Els metodes poden retornar o no un resultat, si no retorna és void. També s’ha de dir que podem retornar un resultat sense return, fent una referencia en el programa i cmbiant la variable principal.

### Exemple enviar per referencia

```csharp
static void Main(string[] args)
    {
        int numero = 14;
        SumaUn(numero); // pas per valor
        Console.WriteLine("El valor és " + numero); // mostra 14
        SumaUn(ref numero); // pas per referència
        Console.WriteLine("El valor és " + numero); // mostra 15
    }
    static void SumaUn(int n)
    {
        n++;
    }
    static void SumaUn(ref int n)
    {
        n++; // al rebre la referència on està emmagatzemada la variable, estem modificant la original
    }
```

Palabra clave **`var`** se usa para declarar una variable sin especificar el tipo de dato. En su lugar, el compilador infiere el tipo de dato a partir de la expresión que se encuentra en el lado derecho de la instrucción de inicialización. Por ejemplo, en lugar de escribir **`int edad = 5;`**, puedes escribir **`var edad = 5;`** y el compilador entenderá que **`edad`** es una variable de tipo **`int`**.

```csharp
var nombre = "Luis";
        var calle = "Av, 5";
        var numero = 10;
        var clasificacion = 8.5;
        var lletra = "A";
        int numeor2 = 6;
```

La palabra clave out se usa para pasar argumentos a métodos como un tipo de referencia. Esto significa que el parámetro formal en el método es un alias para el argumento que se pasa, y cualquier operación en el parámetro se realiza en el argumento. Es similar a la palabra clave ref, excepto que ref requiere que la variable se inicialice antes de pasarla.

A continuació exemples de metodes que fan coses:

### És parell ?

```csharp
static void Main(string[] args) {
        int i;
        for (i = 0; i <= 10; i++) {
            if (EsParell(i)){
                Console.WriteLine(i + " és parell");
            } else {
                Console.WriteLine(i + " és senar");
            }
        }
    }
    static bool EsParell(int n){
        return (n % 2 == 0);
    }
```

### Preguntar per un valor

```csharp
static void Main(string[] args){
	Console.WriteLine("Demanar una nota");
	Console.WriteLine("Introdueix la teva nota");
	double nota = Convert.ToInt32(Console.ReadLine());
	nota(notaa);
}
static void nota(double notaa) {
	Console.WriteLine("La teva nota és: " + notaa);
}
```

### Validar un valor

```csharp
static void Main(string[] args){
	Console.WriteLine("Demanar una nota");
	Console.WriteLine("Introdueix la teva nota");
	double notaa = Convert.ToInt32(Console.ReadLine());
	nota(notaa);
}
static bool validarnota(double notaa) {
        if (notaa >= 0 && notaa <= 10) {
            return true;
        } else {
            return false;
        }
    }

//Si es vol validar una lletra, char, podria ser de la següent manera:
static void respostavalida() {                 
        Console.WriteLine("Introdueix una resposta de 's' o 'n': ");
        char valor = Console.ReadKey().KeyChar;
        validarresposta(valor);
    }
    static void validarresposta(char valor) {
        if (valor == 's' || valor == 'S') {
            Console.WriteLine("\n La teva resposta és vàlida");
        } else if (valor == 'n' || valor == 'N') {
            Console.WriteLine("\n La teva resposta és vàlida");
        } else {
            Console.WriteLine("\n La teva resposta és invàlida");
        }
    }
```

### Operacions de suma, resta, multiplicar, restar

```csharp
static void Main(string[] args)	
	{
		int a, b;
		Console.WriteLine($"1.-Sumar\n2.-Resta\n3.-Multiplicar\n4.-Dividir");
		a=Convert.ToInt32(Console.ReadLine());

		Console.Clear();
		switch (a){
			case 1:
				suma();
				break;

			case 2:
				Console.WriteLine(resta());
				break;
			
			case 3:
				a=Demanar();
				b=Demanar();
				mult(a, b);
				break;

			case 4:
				a=Demanar();
				b=Demanar();
				Console.WriteLine(div(a, b));
				break;

			default:
			break;
		}
		static int Demanar(){
			int a;
			Console.WriteLine("Dona'm un número");
			return a=Convert.ToInt32(Console.ReadLine());
		}
		static void suma(){
            int a, b;
            Console.WriteLine("Dona'm dos números");
            a=Convert.ToInt32(Console.ReadLine());
            b=Convert.ToInt32(Console.ReadLine());
            Console.WriteLine(a+b);
		}

		static int resta(){
            int a, b;
            Console.WriteLine("Dona'm dos números");
            a=Convert.ToInt32(Console.ReadLine());
            b=Convert.ToInt32(Console.ReadLine());
            return a-b;
		}
		static void mult(int a, int b){
			Console.WriteLine(a*b);
		}
		static int div(int a, int b)=>a/b;
	}
```

### Multiplicar a base de sumes

```csharp
static void Main(string[] args)	{               
                Console.WriteLine("Introdueix el primer  valor --> ");
                double valorS1 = Convert.ToInt32(Console.ReadLine());
                Console.WriteLine("Introdueix el segon valor --> ");
                double valorS2 = Convert.ToInt32(Console.ReadLine());

                double valorS = producte(valorS1, valorS2);
                Console.WriteLine($"El teu resultat és {valorS}");
}
static double producte(double valorS1, double ValorS2 ) {
        double resultat = 0;
        for (int i = 0; i < ValorS2 ; i++) {
            resultat = resultat + valorS1 ;
        }
        return resultat;
}
```

### Dividir a base de restes

```csharp
//Demanar Dades
                Console.WriteLine("Introdueix el primer  valor --> ");
                int valorR1 = Convert.ToInt32(Console.ReadLine());
                int valorR2;
                do {
                    Console.WriteLine("Introdueix el segon valor --> ");
                    valorR2 = Convert.ToInt32(Console.ReadLine());
                }while (valorR2 == 0);
                //Rebre Dades
                int valord = div(valorR1, valorR2);
                Console.WriteLine($"El resultat de la divisió és {valord}");
static int div(int valorR1, int valorR2 ) {
        int residu = valorR1;
        int quocient = 0;
        while (residu >= valorR2) {
            residu = residu - valorR2;
            quocient++;
        }
        return quocient;
    }
```

### Mètode que donat un número calculi la suma del 1 al N

```csharp
//Demanar Dades
                Console.WriteLine("Introdueix un valor--> ");
                double valorM1 = Convert.ToInt32(Console.ReadLine());
                //Rebre Dades
                double valorM = producte1n(valorM1);
                Console.WriteLine($"El teu resultat és {valorM}");
static double suma1n(double valorN1) {
        double resultat = 0;
        for (int i = 1; i <= valorN1; i++) {
            resultat = resultat + i ;
        }
        return resultat;
    }
```

### Mètode que donat un número calculi el producte del 1 al N

```csharp
//Demanar Dades
                Console.WriteLine("Introdueix un valor--> ");
                double valorN1 = Convert.ToInt32(Console.ReadLine());
                //Rebre Dades
                double valorn = suma1n(valorN1);
                Console.WriteLine($"El teu resultat és {valorn}");
static double producte1n(double valorM1) {
        double resultat = 1;
        for (int i = 1; i <= valorM1; i++) {
            resultat = resultat * i ;
        }
        return resultat;
    }
```

### Mètode que donat un número N calculi els seus divisors

```csharp
								
								//Demanar Dades
                Console.WriteLine("Introdueix un valor--> ");
                double valorD = Convert.ToInt32(Console.ReadLine());
                //Rebre Dades
                string valorDF = dividirN(valorD);
                Console.WriteLine($"El teu resultat {valorDF}");
static string dividirN(double valorD) {
        string resultat = "són: ";
        for (double i = 1; i < valorD; i++) {
            if (valorD % i == 0) {
                resultat = resultat + $"- {i} -";
            }
        }
        return resultat;
    }
```

---

### Mètode que donat un número N compti els divisors que té

```csharp
static double divisors(double valorD){
        double resultat = 1;
        for (double i = 1; i < valorD; i++){
            if (valorD % i == 0){
                resultat++;
            }
        }
        return resultat;
```

### Mètode que donat un número N miri si un número és primer

```csharp
static string primer(double valorP1){
        string primer = "És primer";
        if (valorP1 < 2){
            primer = "No és primer";
        }else{
            for (int i = 2; i <= Math.Sqrt(valorP1); i++){
                if (valorP1 % i == 0){
                    primer = "No és primer";
                    break;
                }
            }
        }
        return primer;
    }
```

### Mètode que donat un número enter N compti quantes xifres té

```csharp
static double Xifras(double valorN1){
        double xifras = 0;
        if (valorN1 == 0){
            xifras = 1;
        }else{
            while (valorN1 != 0){
                xifras++;
                valorN1 /= 10;
            }
        }
        return xifras;
    }
```

### Mètode que donat un número enter N sumi les seves xifres

```csharp
int suma = 0;
    while (valorM1 != 0)
    {
        suma = suma + valorM1 % 10;
        valorM1 = valorM1 / 10;
    }
    return suma;
```

### Mètode que donat un número enter mirar si és Capicua

```csharp
static bool Capicua(int valorC){
        int Rev = 0;
        int valor = valorC;
        while (valorC != 0){
            int digito = valorC % 10;
            Rev = (Rev * 10) + digito;
            valorC /= 10;
        }
        if (valor == Rev){
            return true;
        }else{
            return false;
        }
    }
```

---

### Mètode per intercanviar dos valors donats

```csharp
//Demanar Dades
                Console.WriteLine("Introdueix el primer  valor --> ");
                double valorI1 = Convert.ToInt32(Console.ReadLine());
                Console.WriteLine("Introdueix el segon valor --> ");
                double valorI2 = Convert.ToInt32(Console.ReadLine());
                //Rebre Dades
                intercanvi(ref valorI1, ref valorI2);
                Console.WriteLine($"El teu resultat són {valorI1} i {valorI2}");
static void intercanvi(ref double valorI1, ref double valorI2 ) {
        double ajuda;
        ajuda = valorI1;
        valorI1 = valorI2;
        valorI2 = ajuda;
    }
```

### Mètode per mirar si és una lletra

```csharp
static bool lletra(char valorL1){
        bool resposta;
        if (valorL1 >= 'a' && valorL1 <= 'z' || valorL1 >= 'A' && valorL1 <= 'Z' || valorL1 == 'ñ' || valorL1 == 'ç' || valorL1 == 'Ñ' || valorL1 == 'Ç'){
            resposta = true; 
        }else {
            resposta = false;
        }
        return resposta;
    }
```

### Mètode per mirar si és un vocal

```csharp
static bool vocal(char valorV1){
        bool resposta;
        if (valorV1 == 'a' || valorV1 == 'e' || valorV1 == 'i'|| valorV1 == 'o' || valorV1 == 'u' || valorV1 == 'A' || valorV1 == 'E' || valorV1 == 'I'|| valorV1 == 'O' || valorV1 == 'U'){
            resposta = true;
        }else {
            resposta = false;
        }
        return resposta;
    }
```

### Mètode per comprobar si és una consonant utilizant altres dos métodes

```csharp
static bool consonant(char valorC1){
        return !(vocal(valorC1)) && lletra(valorC1);
    }
```

### Mètodes per calcular la mitjana de 3 valors

```csharp
static double mitjana(double valorM1, double valorM2, double valorM3){
        double resposta;
        resposta = (valorM1 + valorM2 + valorM3)/3;
        return resposta;
    }
```

---

## Mètodes recursius

Un mètode recursiu és aquell que es crida a ell mateix.

Exemples de mètodes recursius:

### Factorial

```csharp
static long factorial(long n) {
        if (n == 0) {
            return 1;
        } else {
            return n * factorial(n - 1);
        }
    }
```

## FOREACH

El foreach se utiliza para sacar uno a uno los valores de una lista e imprimirlos por pantalla. 

```csharp
foreach ("tipus de variable" "nom de variable" in "lista")
{
	Console.WriteLine("nom de variable");
}
```

## Arrays

### Pedir valor

```csharp
//Matriu unidimensional
static int[] DemanarValors(int[] taula){
            Console.WriteLine("Introdueix els valors de la taula:");
            for (int i = 0; i < taula.Length; i++){
                Console.Write($"Valor de la posició {i + 1}: ");
                taula[i] = Convert.ToInt32(Console.ReadLine());
            }
				return taula;
        }
//Matriu bidimensional
static int[,] DemanarValors(int[,] taula){
        Console.WriteLine("Introdueix els valors de la taula:");

        for (int fila = 0; fila < 3; fila++){
            for (int columna = 0; columna < 3; columna++){
                Console.Write($"Valor de la fila {fila + 1}, columna {columna + 1}: ");
                taula[fila, columna] = Convert.ToInt32(Console.ReadLine());
            }
        }
			return taula;
    }
//Matriu tridimensional
static int[,,] PedirValores(int[,,] tabla) {
    for (int i = 0; i < tabla.GetLength(0); i++) {
        for (int j = 0; j < tabla.GetLength(1); j++) {
            for (int l = 0; l < tabla.GetLength(2); l++) {
                Console.Write($"Ingrese el valor para tabla[{i},{j},{l}]: ");
                tabla[i, j, l] = Convert.ToInt32(Console.ReadLine());
            }
        }
    }
		return tabla;
}
```

### Mostrar un valor la tridimensional esta mal

```csharp
//Taula unidimensional, un vector
static void Mostrar(int[] taula){
            Console.WriteLine("La taula és:");
            for (int i = 0; i < taula.Length; i++){
                Console.Write(taula[i] + "\t");
                if ((i + 1) % 3 == 0) Console.WriteLine();
            }
        }
//Taula bidimensional
static void Mostrar(int[,] taula){
        Console.WriteLine("La taula és:");
        for (int i = 0; i < taula.GetLength(0); i++){
            for (int columna = 0; columna < taula.GetLenght(1); columna++){
                Console.Write(taula[i, columna] + "\t");
            }
            Console.WriteLine();
        }
    }
//Taula tridimensional
static int[,,] PedirValores(int[,,] taula) {
    for (int i = 0; i < taula.GetLength(0); i++) {
        for (int j = 0; j < taula.GetLength(1); j++) {
            for (int l = 0; l < taula.GetLength(2); l++) {
                Console.Write($"Ingrese el valor para tabla[{i},{j},{l}]: ");
                taula[i, j, l] = int.Parse(Console.ReadLine());
            }
        }
    }
		return tabla;
}
```

/t es un tab

/n es un intro

### Mostrar fins a nElements

```csharp
static void MostrarTaula(int[] taula, int nElements){
            Console.WriteLine($"La taula fins a la posició {nElements} és:");
            for (int i = 0; i < nElements; i++){
                Console.Write(taula[i] + "\t");
                if ((i + 1) % 3 == 0) Console.WriteLine();
            }
            Console.WriteLine();
        }
```

### Omplir amb valor aleatori

```csharp
//Matroiu unidimensional
static void OmplirAleatori(int[] taula){
            Random valorR = new Random();
            for (int i = 0; i < taula.Length; i++){
                taula[i] = valorR.Next(101);
            }
            Mostrar(taula);
        }
//Matriu bidimensional
static void OmplirAleatori(int[,] matriu){
    Random valorR = new Random();
    for (int i = 0; i < matriu.GetLength(0); i++){
        for (int j = 0; j < matriu.GetLength(1); j++){
            matriu[i,j] = valorR.Next(101);
        }
    }
    Mostrar(matriu);
}
//Matriu tridimensional
static void OmplirAleatori(int[,,] matriu){
    Random valorR = new Random();
    for (int i = 0; i < matriu.GetLength(0); i++){
        for (int j = 0; j < matriu.GetLength(1); j++){
            for (int k = 0; k < matriu.GetLength(2); k++){
                matriu[i,j,k] = valorR.Next(101);
            }
        }
    }
    Mostrar(matriu);
}
```

### Ordenar matriu

```csharp
static int[] OrdenarValors(int[] taula){
        Array.Sort(taula);
        return taula;
    }
//Matriz bidimensional
static int[,] OrdenarValores(int[,] taula){
    int filas = taula.GetLength(0);
    int columnas = taula.GetLength(1);

    for (int i = 0; i < filas; i++){
        int[] fila = new int[columnas];
        Array.Copy(taula, i * columnas, fila, 0, columnas);
        Array.Sort(fila);
        for (int j = 0; j < columnas; j++){
            taula.SetValue(fila[j], i, j);
        }
    }
    return taula;
}
//Matriz tridimensional
static int[,,] OrdenarValores(int[,,] taula){
    int capas = taula.GetLength(0);
    int filas = taula.GetLength(1);
    int columnas = taula.GetLength(2);

    for (int k = 0; k < capas; k++){
        for (int i = 0; i < filas; i++){
            int[] fila = new int[columnas];
            for (int j = 0; j < columnas; j++){
                fila[j] = taula[k, i, j];
            }
            Array.Sort(fila);

            for (int j = 0; j < columnas; j++){
                taula.SetValue(fila[j], k, i, j);
            }
        }
    }
    return taula;
}
```

### Sumar matrius

```csharp
//Matriu unidimensional
static double[] SumaVectors(double[] vector1, double[] vector2){
        double[] vectorR = new double[vector1.Length];

        if (vector1.Length == vector2.Length){
            for (int i = 0; i < vector1.Length; i++){
                vectorR[i] = vector1[i] + vector2[i];
            }
        }else{
            Console.WriteLine("Els vectors amb longituds diferents no es poden sumar.");
        }
        return vectorR;
    }
//Matriu bidimensional
static double[,] SumaMatrices(double[,] matriz1, double[,] matriz2){
    int filas = matriz1.GetLength(0);
    int columnas = matriz1.GetLength(1);

    if (filas == matriz2.GetLength(0) && columnas == matriz2.GetLength(1)){
        double[,] matrizR = new double[filas, columnas];

        for (int i = 0; i < filas; i++){
            for (int j = 0; j < columnas; j++){
                matrizR[i,j] = matriz1[i,j] + matriz2[i,j];
            }
        }
        return matrizR;
    }else{
        Console.WriteLine("Les matrius no tenen les mateixes dimensions i no es poden sumar.");
        return null;
    }
}
//Matriz tridimensional
static double[,,] SumaMatrices3D(double[,,] matriz1, double[,,] matriz2){
    int dim1 = matriz1.GetLength(0);
    int dim2 = matriz1.GetLength(1);
    int dim3 = matriz1.GetLength(2);

    if (dim1 == matriz2.GetLength(0) && dim2 == matriz2.GetLength(1) && dim3 == matriz2.GetLength(2)){
        double[,,] matrizR = new double[dim1, dim2, dim3];

        for (int i = 0; i < dim1; i++){
            for (int j = 0; j < dim2; j++){
                for (int k = 0; k < dim3; k++){
                    matrizR[i,j,k] = matriz1[i,j,k] + matriz2[i,j,k];
                }
            }
        }
        return matrizR;
    }else{
        Console.WriteLine("Les matrius no tenen les mateixes dimensions i no es poden sumar.");
        return null;
    }
}
```

### Multiplicar matrius

```csharp
//Matriu unidimensional
static double MultiplicaVectors(double[] vector1, double[] vector2){
        double resultat = 0;

        if (vector1.Length == vector2.Length){
            for (int i = 0; i < vector1.Length; i++){
                resultat += vector1[i] * vector2[i];
            }
        }else{
            Console.WriteLine("Els vectors amb longituds diferents no es poden multiplicar");
        }
        return resultat;
    }
//Matriu bidimensional
static double[,] MultiplicaMatrices(double[,] matriz1, double[,] matriz2) {
    int m1Rows = matriz1.GetLength(0);
    int m1Cols = matriz1.GetLength(1);
    int m2Rows = matriz2.GetLength(0);
    int m2Cols = matriz2.GetLength(1);

    if (m1Cols != m2Rows) {
        Console.WriteLine("No es possible multiplicar aquestes matrius.");
        return null;
    }
    double[,] resultat = new double[m1Rows, m2Cols];

    for (int i = 0; i < m1Rows; i++) {
        for (int j = 0; j < m2Cols; j++) {
            double temp = 0;
            for (int k = 0; k < m1Cols; k++) {
                temp += matriz1[i, k] * matriz2[k, j];
            }
            resultat[i, j] = temp;
        }
    }
    return resultat;
}
//Matriu tridimensional
static double[,,] MultiplicaMatrices3D(double[,,] matriz1, double[,,] matriz2) {
    int m1Rows = matriz1.GetLength(0);
    int m1Cols = matriz1.GetLength(1);
    int m1Depth = matriz1.GetLength(2);
    int m2Cols = matriz2.GetLength(1);
    int m2Depth = matriz2.GetLength(2);
    int m2Rows = matriz2.GetLength(0);

    if (m1Cols != m2Rows || m1Depth != m2Depth) {
        Console.WriteLine("No es possible multiplicar aquestes matrius.");
        return null;
    }
    double[,,] resultat = new double[m1Rows, m2Cols, m2Depth];

    for (int i = 0; i < m1Rows; i++) {
        for (int j = 0; j < m2Cols; j++) {
            for (int k = 0; k < m2Depth; k++) {
                double temp = 0;
                for (int l = 0; l < m1Cols; l++) {
                    temp += matriz1[i, l, k] * matriz2[l, j, k];
                }
                resultat[i, j, k] = temp;
            }
        }
    }
    return resultat;
}
```

### Buscar més gran i més petit

```csharp
//Matriu unidimensional
static int mesgran(int[] vector){
        int gran = vector[0];
        for (int i = 0; i < 5; i++){
            if (vector[i] > gran){
                gran = vector[i];
            }
        }
        return gran;
    }
static int mespetit(int[] vector){
        int petit = vector[0];
        for (int i = 0; i < 5; i++){
            if (vector[i] < petit){
                petit = vector[i];
            }
        }
        return petit;
    }
//Matriu bidimensional
static int maximo(int[][] matriz) {
    int max = matriz[0][0];
    for (int i = 0; i < matriz.length; i++) {
        for (int j = 0; j < matriz[i].length; j++) {
            if (matriz[i][j] > max) {
                max = matriz[i][j];
            }
        }
    }
    return max;
}
static int minimo(int[][] matriz) {
    int min = matriz[0][0];
    for (int i = 0; i < matriz.length; i++) {
        for (int j = 0; j < matriz[i].length; j++) {
            if (matriz[i][j] < min) {
                min = matriz[i][j];
            }
        }
    }
    return min;
}
//Matriu tridimensional
static int maximo(int[][][] matriz) {
    int max = matriz[0][0][0];
    for (int i = 0; i < matriz.length; i++) {
        for (int j = 0; j < matriz[i].length; j++) {
            for (int k = 0; k < matriz[i][j].length; k++) {
                if (matriz[i][j][k] > max) {
                    max = matriz[i][j][k];
                }
            }
        }
    }
    return max;
}
static int minimo(int[][][] matriz) {
    int min = matriz[0][0][0];
    for (int i = 0; i < matriz.length; i++) {
        for (int j = 0; j < matriz[i].length; j++) {
            for (int k = 0; k < matriz[i][j].length; k++) {
                if (matriz[i][j][k] < min) {
                    min = matriz[i][j][k];
                }
            }
        }
    }
    return min;
}
```

### Varios

```csharp
//Matriz unidimensionales
static void Main(string[] args)
    {
        int[] numbers = { 3, 1, 4, 1, 5, 9, 2, 6, 5, 3 }; // Crear un array
        AccessArray(numbers); // Acceder a elementos en un array
        TraverseArray(numbers); // Recorrer un array
        SortArray(numbers); // Ordenar un array
        SearchArray(numbers, 6); // Buscar un elemento en un array
        CopyArray(numbers); // Copiar un array
    }

    static void AccessArray(int[] arr)
    {
        int thirdNumber = arr[2]; // Acceder a elementos en un array
        Console.WriteLine($"El tercer número en el array es: {thirdNumber}");
    }

    static void TraverseArray(int[] arr)
    {
        foreach (int number in arr) // Recorrer un array
        {
            Console.Write($"{number} ");
        }
        Console.WriteLine();
    }

    static void SortArray(int[] arr)
    {
        Array.Sort(arr); // Ordenar un array
        Console.Write("El array ordenado es: ");
        TraverseArray(arr);
    }

    static void SearchArray(int[] arr, int num)
    {
        int index = Array.IndexOf(arr, num); // Buscar un elemento en un array
        if (index != -1)
        {
            Console.WriteLine($"El número {num} se encuentra en la posición {index} del array.");
        }
        else
        {
            Console.WriteLine($"El número {num} no se encuentra en el array.");
        }
    }

    static void CopyArray(int[] arr)
    {
        int[] copy = new int[arr.Length]; // Copiar un array
        Array.Copy(arr, copy, arr.Length);
        Console.Write("El array copiado es: ");
        TraverseArray(copy);
    }
//Matriz bidimensionales
static void Main(string[] args)
    {
        int[,] matrix = {
            { 1, 2, 3 },
            { 4, 5, 6 },
            { 7, 8, 9 }
        }; // Crear un array bidimensional

        AccessArray(matrix); // Acceder a elementos en un array bidimensional
        TraverseArray(matrix); // Recorrer un array bidimensional
    }

    static void AccessArray(int[,] arr)
    {
        int value = arr[1, 2]; // Acceder a elementos en un array bidimensional
        Console.WriteLine($"El valor en la posición (1,2) del array es: {value}");
    }

    static void TraverseArray(int[,] arr)
    {
        for (int i = 0; i < arr.GetLength(0); i++) // Recorrer un array bidimensional
        {
            for (int j = 0; j < arr.GetLength(1); j++)
            {
                Console.Write($"{arr[i, j]} ");
            }
            Console.WriteLine();
        }
    }
```

### Ajuda per visualitzar matrius

- **Separar Strings al mostrar matriu**
    
    string.Join
    
    ```csharp
    string[] names = { "Raul", "Iker", "Aniol" };
    string result = string.Join(",", names);
    ```
    

```jsx
string nombres = "Iker, Raúl, Eric";string[] arrayNombres = nombres.Split(',');
for(int i = 0; i < arrayNombres.Length; i++){    Console.WriteLine(arrayNombres[i].Trim()); // Trim() elimina los espacios en blanco al inicio y final de cada nombre}

```

## Escribir en Fitxers

Llegir un fitxer

Estructura try {}

```csharp
            fitxer = new StreamReader(@".\textprova.txt"); 
            linia = fitxer.ReadLine();
            fitxer.Close(); 
            Console.WriteLine(linia); 
```

```csharp
try {

}catch(Exception e){
	Console.WriteLine(e.Message);
}
```

Escriure en un fitxer

```csharp
StreamWriter fitxer; 
fitxer = new StreamWriter(@".\texto.txt"); 
fitxer.Write("Hola que tal ?");
fitxer.Close();
```