fun main() {
    var s = ""

    while (true) {
        print("Введите строку : ")
        val input = readLine()

        if (!input.isNullOrBlank() && input.all { it.isLetter() }) {
            s = input
            break
        }
        println("Ошибка: введите строку из букв, без цифр и символов.")
    }

    var result = ""
    var current = s[0]
    var count = 1

    for (i in 1..s.lastIndex) {
        if (s[i] == current) count++ else { result += "$current${if (count > 1) count else ""}"; current = s[i]; count = 1 }
    }
    println("Результат: $result$current${if (count > 1) count else ""}")
