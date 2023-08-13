<!DOCTYPE html>
<html>
<head>
    <title>نظام التسجيل والاختبارات</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #060615;
            color: #fff;
            margin: 0;
            padding: 0;
        }
        #container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        h2 {
            text-align: center;
            margin-bottom: 20px;
            color: #ff9900;
        }
        label {
            display: block;
            font-size: 18px;
            margin-bottom: 5px;
            color: #ff9900;
        }
        input[type="text"],
        input[type="date"],
        input[type="email"] {
            width: 100%;
            padding: 10px;
            margin-bottom: 15px;
            border: none;
            border-radius: 5px;
        }
        button {
            background-color: #ff9900;
            color: #fff;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }
        .error-message {
            display: none;
            color: #ff0000;
            font-size: 16px;
        }
        #callUpLetter {
            display: none;
            border: 2px dashed #ff9900;
            padding: 20px;
            border-radius: 5px;
            margin-top: 20px;
            background-color: #101015;
        }
        #callUpLetter h2 {
            color: #ff9900;
            margin-top: 0;
        }
        #callUpLetter p {
            color: #fff;
        }
    </style>
</head>
<body>
    <div id="container">
        <div id="stages">
            <button class="stage-button" id="registrationStageBtn">مرحلة التسجيل</button>
            <button class="stage-button" id="testingStageBtn">مرحلة الاختبارات</button>
            <button class="stage-button" id="resultsStageBtn">مرحلة النتائج</button>
        </div>

        <div id="registration">
            <h2>مرحلة التسجيل</h2>
            <form id="registrationForm">
                    <label for="firstName">الاسم الأول:</label>
                    <input type="text" id="firstName" name="firstName" required>
                <label for="lastName">اللقب:</label>
                <input type="text" id="lastName" name="lastName" required>

                <label for="birthdate">تاريخ الميلاد:</label>
                <input type="date" id="birthdate" name="birthdate" required>

                <label for="birthplace">مكان الميلاد:</label>
                <input type="text" id="birthplace" name="birthplace" required>

                <label for="email">البريد الإلكتروني:</label>
                <input type="email" id="email" name="email" required>

                <button id="registrationBtn">تقديم التسجيل</button>
                <p class="error-message" id="registrationError">عذرًا، لا يمكنك رؤية ورقة الاستدعاء. يرجى إدخال المعلومات الخاصة بك.</p>
            </form>
        </div>نا -->
            </form>
        </div>

        <div id="callUpLetter">
            <h2>ورقة الاستدعاء</h2>
            <p>الاسم: <span id="callUpName"></span></p>
            <p>رقم التسجيل: <span id="registrationNumber"></span></p>
            <p>القسم: القسم 1</p>
            <p>تاريخ الميلاد: <span id="birthdateValue"></span></p>
            <p>مكان الميلاد: <span id="birthplaceValue"></span></p>
            <p>البريد الإلكتروني: <span id="emailValue"></span></p>
            <p>رقم سري: <span id="secretNumber"></span></p>
        </div>
        <div id="testing" style="display:none;">
            <h2>مرحلة الاختبارات</h2>
            <p id="testMessage" style="color: red; font-size: 16px;"></p>
            <div id="test" style="display: none;">
                <form id="questionsForm">
                    <!-- ... أسئلة الاختبار ... -->
                    <button id="submitTestBtn">تقديم الاختبار</button>
                </form>
            </div>
        </div>

    </div>

    <script src="script.js"></script>
    <script>

        document.getElementById('submitTestBtn').addEventListener('click', function(event) {
            event.preventDefault();
        document.getElementById('registrationForm').addEventListener('submit', function(event) {
            event.preventDefault();

    var firstName = document.getElementById('firstName').value;
    var lastName = document.getElementById('lastName').value;
    var birthdate = document.getElementById('birthdate').value;
    var birthplace = document.getElementById('birthplace').value;
    var email = document.getElementById('email').value;

    // التحقق من سن الشخص
    var birthYear = new Date(birthdate).getFullYear();
    var currentYear = new Date().getFullYear();
    var age = currentYear - birthYear;

    if (age < 12) {
        alert("لا يمكنك التسجيل، أنت لست في سن القانوني.");
        return;
    }

    // إنشاء أرقام عشوائية لورقة الاستدعاء
    var registrationNumber = Math.floor(Math.random() * (2364789 - 216978 + 1)) + 216978;
    var secretNumber = Math.floor(Math.random() * (25985 - 1235 + 1)) + 1235;

    // عرض ورقة الاستدعاء
    document.getElementById('callUpName').textContent = firstName + ' ' + lastName;
    document.getElementById('registrationNumber').textContent = registrationNumber;
    document.getElementById('birthdateValue').textContent = birthdate;
    document.getElementById('birthplaceValue').textContent = birthplace;
    document.getElementById('emailValue').textContent = email;
    document.getElementById('secretNumber').textContent = secretNumber;
    document.getElementById('callUpLetter').style.display = 'block';
    
});
// مزيد من التعليمات الخاصة بالتبديل بين المراحل والاختبارات وما إلى ذلك
</script></12>
</body>
</html>
