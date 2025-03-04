<html lang="vi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nhắc Nhở Thời Khóa Biểu</title>
    <style>
        /* Phong cách Galaxy */
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background: radial-gradient(circle, #0f2027, #203a43, #2c5364);
            color: white;
            overflow-x: hidden;
        }

        .container {
            max-width: 800px;
            margin: 50px auto;
            padding: 20px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.7);
            text-align: center;
        }

        h1 {
            font-size: 2.5em;
            text-shadow: 2px 2px 8px rgba(255, 255, 255, 0.8);
            color: #ffcc00;
        }

        h2 {
            color: #f39c12;
            margin-bottom: 20px;
            text-shadow: 2px 2px 8px rgba(255, 255, 255, 0.7);
        }

        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px 5px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            color: white;
            background: linear-gradient(45deg, #8e44ad, #3498db);
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            transition: all 0.3s ease;
        }

        button:hover {
            background: linear-gradient(45deg, #3498db, #8e44ad);
            transform: translateY(-3px);
        }

        input {
            padding: 10px;
            width: 70%;
            margin: 10px 0;
            border-radius: 5px;
            border: none;
            font-size: 16px;
        }

        .alert {
            margin-top: 20px;
            padding: 15px;
            background: #16a085;
            border-radius: 5px;
            font-size: 16px;
            display: none;
            color: white;
        }

        ul {
            list-style: none;
            padding: 0;
            margin: 20px 0;
        }

        ul li {
            background: rgba(255, 255, 255, 0.3);
            margin: 5px 0;
            padding: 10px;
            border-radius: 5px;
            color: white;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        ul li span {
            color: red;
            cursor: pointer;
            font-weight: bold;
        }

        /* Thời khóa biểu */
        .timetable-container {
            margin-top: 30px;
            background: rgba(255, 255, 255, 0.1);
            padding: 15px;
            border-radius: 10px;
        }

        .timetable-table {
            width: 100%;
            border-collapse: collapse;
            margin-top: 15px;
        }

        .timetable-table th,
        .timetable-table td {
            border: 1px solid #ddd;
            padding: 10px;
            text-align: center;
        }

        .timetable-table th {
            background-color: #34495e;
            color: white;
        }

        .timetable-table td {
            background-color: #2c3e50;
        }

        .timetable-table td input {
            width: 100%;
            background-color: transparent;
            color: white;
            border: none;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>✨ WorkMate 10.12 ✨</h1>
        <p>Ứng dụng nhắc nhở lịch học,thời khóa biểu.</p>

        <!-- Nhắc nhở mặc áo đoàn -->
        <section>
            <h2>📢 Nhắc nhở Mặc Áo Đoàn vào mỗi thứ 6 hàng tuần</h2>
            <button id="startReminder">✔️ Bật Nhắc Nhở</button>
            <button id="stopReminder">❌ Tắt Nhắc Nhở</button>
            <div id="alert" class="alert">🔔 Hôm nay là thứ 6! Đừng quên mặc áo đoàn nhé!</div>
        </section>

        <!-- Quản lý lịch trình -->
        <section>
            <h2>📅 Lịch Trình & Nhắc Nhở</h2>
            <input type="text" id="taskInput" placeholder="Nhập công việc hoặc cần nhắc nhở...">
            <input type="time" id="taskTime">
            <button id="addTask">➕ Thêm</button>
            <ul id="taskList"></ul>
        </section>

        <!-- Thời khóa biểu -->
        <section class="timetable-container">
            <h2>🗓 Thời Khóa Biểu</h2>
            <table class="timetable-table" id="timetable">
                <thead>
                    <tr>
                        <th>Thứ</th>
                        <th>Buổi sáng</th>
                        <th>Buổi chiều</th>
                    </tr>
                </thead>
                <tbody>
                    <!-- Các ngày trong tuần -->
                    <tr>
                        <td>Thứ 2</td>
                        <td>
                            <input type="text" id="mondayAM1" placeholder="Môn 1"><br>
                            <input type="text" id="mondayAM2" placeholder="Môn 2"><br>
                            <input type="text" id="mondayAM3" placeholder="Môn 3"><br>
                            <input type="text" id="mondayAM4" placeholder="Môn 4"><br>
                            <input type="text" id="mondayAM5" placeholder="Môn 5">
                        </td>
                        <td>
                            <input type="text" id="mondayPM1" placeholder="Môn 1"><br>
                            <input type="text" id="mondayPM2" placeholder="Môn 2"><br>
                            <input type="text" id="mondayPM3" placeholder="Môn 3"><br>
                            <input type="text" id="mondayPM4" placeholder="Môn 4"><br>
                            <input type="text" id="mondayPM5" placeholder="Môn 5">
                        </td>
                    </tr>
                    <tr>
                        <td>Thứ 3</td>
                        <td>
                            <input type="text" id="tuesdayAM1" placeholder="Môn 1"><br>
                            <input type="text" id="tuesdayAM2" placeholder="Môn 2"><br>
                            <input type="text" id="tuesdayAM3" placeholder="Môn 3"><br>
                            <input type="text" id="tuesdayAM4" placeholder="Môn 4"><br>
                            <input type="text" id="tuesdayAM5" placeholder="Môn 5">
                        </td>
                        <td>
                            <input type="text" id="tuesdayPM1" placeholder="Môn 1"><br>
                            <input type="text" id="tuesdayPM2" placeholder="Môn 2"><br>
                            <input type="text" id="tuesdayPM3" placeholder="Môn 3"><br>
                            <input type="text" id="tuesdayPM4" placeholder="Môn 4"><br>
                            <input type="text" id="tuesdayPM5" placeholder="Môn 5">
                        </td>
                    </tr>
                    <tr>
                        <td>Thứ 4</td>
                        <td>
                            <input type="text" id="wednesdayAM1" placeholder="Môn 1"><br>
                            <input type="text" id="wednesdayAM2" placeholder="Môn 2"><br>
                            <input type="text" id="wednesdayAM3" placeholder="Môn 3"><br>
                            <input type="text" id="wednesdayAM4" placeholder="Môn 4"><br>
                            <input type="text" id="wednesdayAM5" placeholder="Môn 5">
                        </td>
                        <td>
                            <input type="text" id="wednesdayPM1" placeholder="Môn 1"><br>
                            <input type="text" id="wednesdayPM2" placeholder="Môn 2"><br>
                            <input type="text" id="wednesdayPM3" placeholder="Môn 3"><br>
                            <input type="text" id="wednesdayPM4" placeholder="Môn 4"><br>
                            <input type="text" id="wednesdayPM5" placeholder="Môn 5">
                        </td>
                    </tr>
                    <tr>
                        <td>Thứ 5</td>
                        <td>
                            <input type="text" id="thursdayAM1" placeholder="Môn 1"><br>
                            <input type="text" id="thursdayAM2" placeholder="Môn 2"><br>
                            <input type="text" id="thursdayAM3" placeholder="Môn 3"><br>
                            <input type="text" id="thursdayAM4" placeholder="Môn 4"><br>
                            <input type="text" id="thursdayAM5" placeholder="Môn 5">
                        </td>
                        <td>
                            <input type="text" id="thursdayPM1" placeholder="Môn 1"><br>
                            <input type="text" id="thursdayPM2" placeholder="Môn 2"><br>
                            <input type="text" id="thursdayPM3" placeholder="Môn 3"><br>
                            <input type="text" id="thursdayPM4" placeholder="Môn 4"><br>
                            <input type="text" id="thursdayPM5" placeholder="Môn 5">
                        </td>
                    </tr>
                    <tr>
                        <td>Thứ 6</td>
                        <td>
                            <input type="text" id="fridayAM1" placeholder="Môn 1"><br>
                            <input type="text" id="fridayAM2" placeholder="Môn 2"><br>
                            <input type="text" id="fridayAM3" placeholder="Môn 3"><br>
                            <input type="text" id="fridayAM4" placeholder="Môn 4"><br>
                            <input type="text" id="fridayAM5" placeholder="Môn 5">
                        </td>
                        <td>
                            <input type="text" id="fridayPM1" placeholder="Môn 1"><br>
                            <input type="text" id="fridayPM2" placeholder="Môn 2"><br>
                            <input type="text" id="fridayPM3" placeholder="Môn 3"><br>
                            <input type="text" id="fridayPM4" placeholder="Môn 4"><br>
                            <input type="text" id="fridayPM5" placeholder="Môn 5">
                        </td>
                    </tr>
                    <tr>
                        <td>Thứ 7</td>
                        <td>
                            <input type="text" id="saturdayAM1" placeholder="Môn 1"><br>
                            <input type="text" id="saturdayAM2" placeholder="Môn 2"><br>
                            <input type="text" id="saturdayAM3" placeholder="Môn 3"><br>
                            <input type="text" id="saturdayAM4" placeholder="Môn 4"><br>
                            <input type="text" id="saturdayAM5" placeholder="Môn 5">
                        </td>
                        <td>
                            <input type="text" id="saturdayPM1" placeholder="Môn 1"><br>
                            <input type="text" id="saturdayPM2" placeholder="Môn 2"><br>
                            <input type="text" id="saturdayPM3" placeholder="Môn 3"><br>
                            <input type="text" id="saturdayPM4" placeholder="Môn 4"><br>
                            <input type="text" id="saturdayPM5" placeholder="Môn 5">
                        </td>
                    </tr>
                </tbody>
            </table>
        </section>
        <footer>
            <p>✨ Made by Van Anh Thong ✨</p>
        </footer>

        <!-- Nút lưu -->
        <button onclick="saveTimetable()">Lưu Thời Khóa Biểu</button>

        <!-- Thông báo -->
        <div class="alert" id="alertMessage">
            Đã lưu thành công thời khóa biểu!
        </div>

    </div>

    <script>
        // Nhắc mặc áo đoàn
        let reminderInterval;

        function isFriday() {
            const today = new Date();
            return today.getDay() === 5; // Thứ 6 là ngày 5
        }

        document.getElementById("startReminder").addEventListener("click", () => {
            if (!reminderInterval) {
                reminderInterval = setInterval(() => {
                    const now = new Date();
                    if (isFriday() && now.getHours() === 8 && now.getMinutes() === 0) {
                        document.getElementById("alert").style.display = "block";
                    }
                }, 60000); // Kiểm tra mỗi phút
                alert("Nhắc nhở đã được bật!");
            }
        });

        document.getElementById("stopReminder").addEventListener("click", () => {
            if (reminderInterval) {
                clearInterval(reminderInterval);
                reminderInterval = null;
                alert("Nhắc nhở đã được tắt!");
            }
        });

        // Quản lý lịch trình và báo thức
        const taskList = document.getElementById("taskList");

        document.getElementById("addTask").addEventListener("click"), () => {
            const taskInput = document.getElementById("taskInput");
            const taskTime = document.getElementById("taskTime");
            const taskText = taskInput.value.trim();
            const time = taskTime.value;

            if (!taskText || !time) {
                alert("Vui lòng nhập công việc và thời gian!");
                return;
            }

            // Tạo công việc
            const listItem = document.createElement("li");
            listItem.innerHTML = `${taskText} - <strong>${time}</strong> <span>X</span>`;

            // Xóa công việc khi nhấn "X"
            listItem.querySelector("span").addEventListener("click", () => {
                taskList.removeChild(listItem);
            });

            taskList.appendChild(listItem);

            // Đặt báo thức
            const [hour, minute] = time.split(":").map(Number);
            const now = new Date();
            const Date = new Date(now.getFullYear(), now.getMonth(), now.getDate(), hour, minute);

            const timeToAlert = taskTime.getTime() - now.getTime();
            if (timeToAlert > 0) {
                setTimeout(() => {
                    alert(`⏰ Nhắc nhở: ${taskText}`);
                }, timeToAlert);
            }

            taskInput.value = "";
            taskTime.value = "";
        };
        function saveTimetable() {
            const timetable = {
                Monday: {
                    AM: [
                        document.getElementById('mondayAM1').value,
                        document.getElementById('mondayAM2').value,
                        document.getElementById('mondayAM3').value,
                        document.getElementById('mondayAM4').value,
                        document.getElementById('mondayAM5').value,
                    ],
                    PM: [
                        document.getElementById('mondayPM1').value,
                        document.getElementById('mondayPM2').value,
                        document.getElementById('mondayPM3').value,
                        document.getElementById('mondayPM4').value,
                        document.getElementById('mondayPM5').value,
                    ],
                },
                Tuesday: {
                    AM: [
                        document.getElementById('tuesdayAM1').value,
                        document.getElementById('tuesdayAM2').value,
                        document.getElementById('tuesdayAM3').value,
                        document.getElementById('tuesdayAM4').value,
                        document.getElementById('tuesdayAM5').value,
                    ],
                    PM: [
                        document.getElementById('tuesdayPM1').value,
                        document.getElementById('tuesdayPM2').value,
                        document.getElementById('tuesdayPM3').value,
                        document.getElementById('tuesdayPM4').value,
                        document.getElementById('tuesdayPM5').value,
                    ],
                },
                Wednesday: {
                    AM: [
                        document.getElementById('wednesdayAM1').value,
                        document.getElementById('wednesdayAM2').value,
                        document.getElementById('wednesdayAM3').value,
                        document.getElementById('wednesdayAM4').value,
                        document.getElementById('wednesdayAM5').value,
                    ],
                    PM: [
                        document.getElementById('wednesdayPM1').value,
                        document.getElementById('wednesdayPM2').value,
                        document.getElementById('wednesdayPM3').value,
                        document.getElementById('wednesdayPM4').value,
                        document.getElementById('wednesdayPM5').value,
                    ],
                },
                Thursday: {
                    AM: [
                        document.getElementById('thursdayAM1').value,
                        document.getElementById('thursdayAM2').value,
                        document.getElementById('thursdayAM3').value,
                        document.getElementById('thursdayAM4').value,
                        document.getElementById('thursdayAM5').value,
                    ],
                    PM: [
                        document.getElementById('thursdayPM1').value,
                        document.getElementById('thursdayPM2').value,
                        document.getElementById('thursdayPM3').value,
                        document.getElementById('thursdayPM4').value,
                        document.getElementById('thursdayPM5').value,
                    ],
                },
                Friday: {
                    AM: [
                        document.getElementById('fridayAM1').value,
                        document.getElementById('fridayAM2').value,
                        document.getElementById('fridayAM3').value,
                        document.getElementById('fridayAM4').value,
                        document.getElementById('fridayAM5').value,
                    ],
                    PM: [
                        document.getElementById('fridayPM1').value,
                        document.getElementById('fridayPM2').value,
                        document.getElementById('fridayPM3').value,
                        document.getElementById('fridayPM4').value,
                        document.getElementById('fridayPM5').value,
                    ],
                },
                Saturday: {
                    AM: [
                        document.getElementById('saturdayAM1').value,
                        document.getElementById('saturdayAM2').value,
                        document.getElementById('saturdayAM3').value,
                        document.getElementById('saturdayAM4').value,
                        document.getElementById('saturdayAM5').value,
                    ],
                    PM: [
                        document.getElementById('saturdayPM1').value,
                        document.getElementById('saturdayPM2').value,
                        document.getElementById('saturdayPM3').value,
                        document.getElementById('saturdayPM4').value,
                        document.getElementById('saturdayPM5').value,
                    ],
                },
            };

            // Hiển thị thông báo
            document.getElementById('alertMessage').style.display = 'block';
            
            // Ẩn thông báo sau 3 giây
            setTimeout(() => {
                document.getElementById('alertMessage').style.display = 'none';
            }, 2000);
        }
    </script>
</body>
</html>
