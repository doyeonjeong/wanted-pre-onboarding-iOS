# ๐ ์ํฐ๋ ํ๋ฆฌ์จ๋ณด๋ฉ ์ฑ๋ฆฐ์ง iOS๊ณผ์  ์ฌ์ ๊ณผ์ 
|**ํ๋ก์ ํธ๋ช**|MyCreditManager|
|:---:|:---|
|**ํ๋ก์ ํธ ์๊ฐ**|์ฑ์  ๊ด๋ฆฌ ํ๋ก๊ทธ๋จ|
|**์ฌ์ฉ ์ธ์ด**|Swift|
|**ํ๊ฒฝ**|Xcode ๊ธฐ๋ณธ ํํ๋ฆฟ ์ค [ macOS - Command Line Tool ]|
|**์์๊ธฐ๊ฐ**|22.11.22 ~ 22.11.23|
|**ํ๋ก๊ทธ๋จ ๋ฉ๋ด**|- ํ์ ์ถ๊ฐ <br>- ํ์ ์ญ์  <br>- ์ฑ์  ์ถ๊ฐ(๋ณ๊ฒฝ) <br>- ์ฑ์  ์ญ์  <br>- ํ์  ๋ณด๊ธฐ <br>- ์ข๋ฃ <br>- ์์ธ์ฒ๋ฆฌ|
|**ํ๋ก๊ทธ๋จ ๋์์กฐ๊ฑด**|- ์ฌ์ฉ์๊ฐ ์ข๋ฃ ๋ฉ๋ด๋ฅผ ์ ํํ๊ธฐ ์ ๊น์ง๋ ๊ณ์ํด์ ์ฌ์ฉ์์ ์๋ ฅ์ ๋ฐ์ต๋๋ค <br>- ๋ฉ๋ด์ ํ์ ํฌํจํ ๋ชจ๋  ์๋ ฅ์ ์ซ์ ๋๋ ์๋ฌธ์ผ๋ก ๋ฐ์ต๋๋ค|
|**์ฑ์ ๋ณ ์ ์**|- A+ (4.5์ ) / A (4์ ) <br>- B+ (3.5์ ) / B (3์ ) <br>- C+ (2.5์ ) / C (2์ ) <br>- D+ (1.5์ ) / D (1์ ) <br>- F (0์ )|
|**ํ์ **|- ๊ฐ ๊ณผ๋ชฉ์ ์ ์ ์ด ํฉ / ๊ณผ๋ชฉ ์ <br>- ์ต๋ ์์์  2๋ฒ์งธ ์๋ฆฌ๊น์ง ์ถ๋ ฅ <br> - ์) 3.75 / 4.1 / 2|

---

## ์ปค๋ฐ ๋ฉ์ธ์ง
|**Gitmoji**|**Description**|
|:---:|:---|
|๐|**ํ๋ก์ ํธ ์์ฑ**|
|โจ|**์๋ก์ด ๊ธฐ๋ฅ** ์ถ๊ฐ|
|๐จ|์ฝ๋์ย **ํ์ / ๊ตฌ์กฐ** ๊ฐ์ |
|๐ก|**์๋ก์ด ์์ด๋์ด** ๋๋ **์ฃผ์ ์์ **|
|โป๏ธ|์ฝ๋ย **๋ฆฌํฉํ ๋ง**|
|๐|**๋ฌธ์** ์ถ๊ฐ ๋๋ ์์ |

---

## ํ๋ก๊ทธ๋จ ๋์ ๊ณผ์ 
### ์ ๋ณด ๊ตฌ์กฐ
```swift
// ํ์ ์ ๋ณด Struct
struct Student {
    let name: String
    var subject: [Subject]
}

// ๊ณผ๋ชฉ ์ ๋ณด Struct
struct Subject {
    let title: String
    var grade: String
}

// ํ์ ์ ๋ณด ์ ์ฅ
var studentInfo: [Student] = [] // [MyCreditManager.Student(name: "ํ์์ด๋ฆ", subject: [])]
```

### ํ์ ์ถ๊ฐ
<p align="center">
    <img width="100%" alt="แแกแจแแขแผ แแฎแแก" src="https://user-images.githubusercontent.com/108422901/203584493-50144859-4120-43bc-b20e-377b179fa43f.png">
</p>

```swift
// ์ถ๊ฐํ  ํ์ ์ด๋ฆ ์๋ ฅ
let name = readLine() ?? ""
if nameCheck(name) { // validation check : ์ด๋ฆ ํ์์ ์ ํฉํ๋ค๋ฉด true
    insertStudent(name)
} else {
    print("์๋ ฅ์ด ์๋ชป๋์์ต๋๋ค. ๋ค์ ํ์ธํด์ฃผ์ธ์.")
}

// ์ ๊ท์ : ์์ด ๋๋ฌธ์๋ก ์์, 2๋ฒ์งธ ์ดํ ์์ด ์๋ฌธ์ 1~20๊ฐ, ๊ณต๋ฐฑ ์์ด ํ ๋จ์ด
func nameCheck(_ name: String) -> Bool {
    return (name.range(of: #"^(?:[A-Z][a-z]{1,20}){1}$"#, options: .regularExpression) != nil) ? true : false
}

// ํ์ ์ ๋ณด ๋ฑ๋ก
func insertStudent(_ name: String) {
    // studentInfo์ ๋ชจ๋  ์ ๋ณด ์ค name์ด ํ์ฌ name๊ณผ ์ผ์นํ๋ ์ ๋ณด๊ฐ ์กด์ฌํ๋ ๊ฒฝ์ฐ
    if studentInfo.filter({$0.name == name}).count != 0 {
        print("\(name)์ ์ด๋ฏธ ์กด์ฌํ๋ ํ์์๋๋ค. ์ถ๊ฐํ์ง ์์ต๋๋ค.")
    } else {
        // ์กด์ฌํ์ง ์๋ ๊ฒฝ์ฐ Studentํ ์ ๋ณด๋ฅผ studentInfo์ ์ถ๊ฐ
        let new = Student(name: name, subject: [])
        studentInfo.append(new)
        print("\(name) ํ์์ ์ถ๊ฐํ์ต๋๋ค.")
    }
}
```

### ํ์ ์ญ์ 
<p align="center">
    <img width="100%" alt="แแกแจแแขแผ ์ญ์ " src="https://user-images.githubusercontent.com/108422901/203584621-6ebea281-08dd-40d3-baff-defafde263f5.png">
</p>

```swift
// ์ญ์ ํ  ํ์ ์ด๋ฆ ์๋ ฅ
let name = readLine() ?? ""
if nameCheck(name) {
    deleteStudent(name)
} else {
    print("์๋ ฅ์ด ์๋ชป๋์์ต๋๋ค. ๋ค์ ํ์ธํด์ฃผ์ธ์.")
}

// ํ์ ์ ๋ณด ์ญ์ 
func deleteStudent(_ name: String) {
    // studentInfo์ ํด๋น ์ ๋ณด๊ฐ ์กด์ฌํ๋ฉด ์ญ์ 
    if let index = studentInfo.firstIndex(where: {$0.name == name}) {
        studentInfo.remove(at: index)
        print("\(name) ํ์์ ์ญ์ ํ์์ต๋๋ค.")
    } else {
        print("\(name) ํ์์ ์ฐพ์ง ๋ชปํ์ต๋๋ค.")
    }
}
```

### ์ฑ์  ์ถ๊ฐ(๋ณ๊ฒฝ)
<p align="center">
    <img width="100%" alt="์ฑ์  ์ถ๊ฐ(๋ณ๊ฒฝ)" src="https://user-images.githubusercontent.com/108422901/203584617-bf424f99-63d2-4b21-adf9-6d3ff5898ee3.png">
</p>

```swift
// input: String -> array: [String] -> (name, subject, grade)์ผ๋ก ๊ฐ๊ณต
guard let input = readLine() else { break }
let array = input.split(separator: " ").map{ String($0) }
if array.count == 3 {
    let (name, subject, grade) = (array[0], array[1], array[2])
    if gradeCheck(grade) { // validation check : ์ฑ์  ํ์์ ์ ํฉํ๋ค๋ฉด true
        updateGrade(name: name, subject: subject, grade: grade)
    } else {
        print("์ฑ์ ์ด ์์์ ๋ง๊ฒ ์๋ ฅ๋์ง ์์์ต๋๋ค. ๋ค์ ์๋ํด์ฃผ์ธ์.")
    }
} else {
    print("์๋ ฅ์ด ์๋ชป๋์์ต๋๋ค. ๋ค์ ํ์ธํด์ฃผ์ธ์.")
}

// ์ ๊ท์ : A(+-),B(+-),C(+-),D(+-),F
func gradeCheck(_ grade: String) -> Bool {
    var result = false
    if (grade.range(of: #"^[A-DF][+-]?$"#, options: .regularExpression) != nil) {
        if (grade.contains("F")) && (grade.count > 1) {
            return false // ์ฑ์ ์ด F-, F+ ์ด๋ผ๋ฉด false
        }
        result = true
    }
    return result
}

// ์ฑ์  ์ ๋ณด ์๋ฐ์ดํธ
func updateGrade(name:String, subject: String, grade: String) {
    // ํ์ ์กด์ฌ ์ฌ๋ถ ์ฒดํฌ
    if let studentIdx = studentInfo.firstIndex(where: { $0.name == name }) {
        // ๊ณผ๋ชฉ ์กด์ฌ ์ฌ๋ถ ์ฒดํฌ
        if let subjectIdx = studentInfo[studentIdx].subject.firstIndex(where: { $0.title == subject}) {
            // ๊ณผ๋ชฉ์ด ์กด์ฌํ๋ ๊ฒฝ์ฐ ์ฑ์  ์๋ฐ์ดํธ
            studentInfo[studentIdx].subject[subjectIdx].grade = grade
        } else {
            // ๊ณผ๋ชฉ์ด ์กด์ฌํ์ง ์์ ๊ฒฝ์ฐ ๊ณผ๋ชฉ, ์ฑ์  ์ ๋ณด ์ถ๊ฐ
            let newSubjectInfo = Subject(title: subject, grade: grade)
            studentInfo[studentIdx].subject.append(newSubjectInfo)
        }
        print("\(name) ํ์์ \(subject) ๊ณผ๋ชฉ์ด \(grade)๋ก ์ถ๊ฐ(๋ณ๊ฒฝ)๋์์ต๋๋ค.")
    } else {
        print("\(name) ํ์์ ์ฐพ์ง ๋ชปํ์ต๋๋ค.")
    }
}
```

### ์ฑ์  ์ญ์ 
<p align="center">
    <img width="100%" alt="์ฑ์  ์ญ์ " src="https://user-images.githubusercontent.com/108422901/203584602-416b4dc3-e9e8-4e52-bad0-278b1f7555bd.png">
</p>

```swift
// input: String -> array: [String] -> (name, subject)๋ก ๊ฐ๊ณต
guard let input = readLine() else { break }
let array = input.split(separator: " ").map{ String($0) }
if array.count == 2 {
    let (name, subject) = (array[0], array[1])
    deleteGrade(name: name, subject: subject)
} else {
    print("์๋ ฅ์ด ์๋ชป๋์์ต๋๋ค. ๋ค์ ํ์ธํด์ฃผ์ธ์")
}

// ์ฑ์  ์ ๋ณด ์ญ์ 
func deleteGrade(name: String, subject: String) {
    // ํ์ ์กด์ฌ ์ฌ๋ถ ์ฒดํฌ
    if let studentIdx = studentInfo.firstIndex(where: { $0.name == name }) {
        // ๊ณผ๋ชฉ ์กด์ฌ ์ฌ๋ถ ์ฒดํฌ
        if let subjectIdx = studentInfo[studentIdx].subject.firstIndex(where: { $0.title == subject}) {
            // ๊ณผ๋ชฉ์ด ์กด์ฌํ๋ ๊ฒฝ์ฐ ์ญ์ 
            studentInfo[studentIdx].subject.remove(at: subjectIdx)
            print("\(name) ํ์์ \(subject) ๊ณผ๋ชฉ์ ์ฑ์ ์ด ์ญ์ ๋์์ต๋๋ค.")
        } else {
            print("\(name) ํ์์ \(subject) ๊ณผ๋ชฉ์ด ์กด์ฌํ์ง ์์ต๋๋ค.")
        }
    } else {
        print("\(name) ํ์์ ์ฐพ์ง ๋ชปํ์ต๋๋ค.")
    }
}
```

### ํ์  ๋ณด๊ธฐ
<p align="center">
    <img width="100%" alt="ํ์  ๋ณด๊ธฐ" src="https://user-images.githubusercontent.com/108422901/203584607-c3734a63-0d93-4cc6-86fd-948402839bbc.png">
</p>

```swift
// ํ์ ์ ํ์ธํ  ํ์ ์ด๋ฆ ์๋ ฅ
let name = readLine() ?? ""
if nameCheck(name) { // validation check : ์ด๋ฆ ํ์์ ์ ํฉํ๋ค๋ฉด true
    getAverage(name)
} else {
    print("์๋ ฅ์ด ์๋ชป๋์์ต๋๋ค. ๋ค์ ํ์ธํด์ฃผ์ธ์.")
}

// ์ ์ฒด ํ๊ท  ์ ๋ณด
func getAverage(_ name: String) {
    // ํ์ ์กด์ฌ ์ฌ๋ถ ์ฒดํฌ
    if let idx = studentInfo.firstIndex(where: { $0.name == name }) {
        var total: Double = 0.0
        studentInfo[idx].subject.forEach { subjectInfo in
            print("\(subjectInfo.title): \(subjectInfo.grade)")
            total += getScore(subjectInfo.grade)
        }
        let average = String(format: "%.2f", total / Double(studentInfo[idx].subject.count))
        print("ํ์  : \(average)")
    } else {
        print("\(name) ํ์์ ์ฐพ์ง ๋ชปํ์ต๋๋ค.")
    }
}

// ์ฑ์ ์ ์ ์๋ก ๋ณํ
func getScore(_ grade: String) -> Double {
    switch grade {
    case "A+":
        return 4.5
    case "A":
        return 4.0
    case "B+":
        return 3.5
    case "B":
        return 3.0
    case "C+":
        return 2.5
    case "C":
        return 2.0
    case "D+":
        return 1.5
    case "D":
        return 1.0
    default:
        return 0.0
    }
}
```

### ํ๋ก๊ทธ๋จ ์ข๋ฃ
<p align="center">
    <img width="100%" alt="์ข๋ฃ" src="https://user-images.githubusercontent.com/108422901/203584612-88460072-2e2d-4b88-a805-3606a505e1d5.png">
</p>

```swift
var isRun:Bool = true // ํ๋ก๊ทธ๋จ ์คํ ์ํ

while isRun { // isRun์ด true๋ผ๋ฉด ์ ์ฒด ๋ฉ๋ด ์คํ ์ํ
    let input = readLine() ?? ""

    switch input {
    ...
    case "X": // input์ด X๋ผ๋ฉด
            print("ํ๋ก๊ทธ๋จ์ ์ข๋ฃํฉ๋๋ค...")
            isRun = false // isRun์ false๋ก ๋ณ๊ฒฝํ์ฌ ์คํ ์ข๋ฃ
}
```

### ์์ธ์ฒ๋ฆฌ
```swift
// ํ๋ก๊ทธ๋จ ์คํ ์ค
while isRun == true {
let input = readLine() ?? ""
    switch input {
        default: // input์ด 1~5 or X์ ํด๋นํ์ง ์์ผ๋ฉด ์์ธ, ์ฒ์์ผ๋ก ๋์๊ฐ
            print("๋ญ๊ฐ ์๋ ฅ์ด ์๋ชป๋์์ต๋๋ค. 1~5 ์ฌ์ด์ ์ซ์ ํน์ X๋ฅผ ์๋ ฅํด์ฃผ์ธ์.")
    }
}
```
