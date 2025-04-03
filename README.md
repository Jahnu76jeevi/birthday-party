<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Birthday Invitation</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <!-- Home Section -->
    <section id="home" class="section">
        <div class="home-card">
            <h1>Welcome to the Birthday Celebration! 🎉</h1>
            <button onclick="showWelcome()">Click to Enter</button>
            <p id="welcome-message"></p>

            <img src="baby-photo.jpg" alt="Birthday Baby" class="baby-photo">

            <button onclick="showSection('invitation')">View Invitation</button>
        </div>
    </section>

    <!-- Invitation Section -->
    <section id="invitation" class="section hidden">
        <div class="invitation-card">
            <h1>You're Invited! 🎂</h1>
            <p>Join us to celebrate <strong>[SEYON]</strong>'s Birthday!</p>
            <p><strong>Date:</strong> FEBRAUARY 1, 2024</p>
            <p><strong>Time:</strong> 6:00 PM</p>
            <p><strong>Venue:</strong> AKSHU Party Hall</p>

            <!-- Google Map Embed -->
            <iframe 
                src=https://www.google.com/url?sa=i&url=https%3A%2F%2Fwww.amazon.in%2FARTZNew-Photo-Pregnant-Bedroom-Finish%2Fdp%2FB0DFY7K531&psig=AOvVaw0bsAWgz-4wSRTxw2HW4cHU&ust=1743780568576000&source=images&cd=vfe&opi=89978449&ved=0CBIQjRxqFwoTCMDAmfyWvIwDFQAAAAAdAAAAABAE
                width="30" height="20" style="border:0;" allowfullscreen="" loading="speed">
            </iframe>

            <button onclick="showSection('rsvp')">rsvp Now</button>
        </div>
    </section>

    <!-- RSVP Section -->
    <section id="rsvp" class="section hidden">
        <div class="rsvp-card">
            <h1>RSVP for the Birthday Party 🎈</h1>

            <form id="rsvp-form">
                <label for="name">Your Name:</label>
                <input type="text" id="name" required>

                <label for="contact">Contact Number:</label>
                <input type="text" id="contact" required>

                <label>Will you attend?</label>
                <select id="attendance">
                    <option value="yes">Yes, I will be there!</option>
                    <option value="no">Sorry, I can't make it</option>
                </select>

                <button type="button" onclick="submitRSVP()">Submit</button>
            </form>

            <p id="rsvp-message"></p>
        </div>
    </section>

    <script>
        function showWelcome() {
            document.getElementById("welcome-message").innerText = "Welcome to the Birthday Celebration! 🎉";
        }

        function showSection(sectionId) {
            // Hide all sections
            let sections = document.querySelectorAll('.section');
            sections.forEach(section => section.classList.add('hidden'));

            // Show the selected section
            document.getElementById(sectionId).classList.remove('hidden');
        }

        function submitRSVP() {
            let name = document.getElementById("name").value;
            let contact = document.getElementById("contact").value;
            let attendance = document.getElementById("attendance").value;

            if (name === "" || contact === "") {
                document.getElementById("rsvp-message").innerText = "Please fill out all fields.";
            } else {
                document.getElementById("rsvp-message").innerText = `Thank you, ${name}! Your RSVP is submitted.`;
            }
        }
    </script>

    <style>
        body {
            font-family: Arial, sans-serif;
            background-color:blueviolet;
            text-align: center;
            padding: 50px;
        }

        .home-card, .invitation-card, .rsvp-card {
            background: white;
            padding: 20px;
            max-width: 400px;
            margin: auto;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }

        h1 {
            color: #ff4500;
        }

        button {
            background-color: #ff4500;
            color: white;
            border: none;
            padding: 10px 15px;
            cursor: pointer;
            border-radius: 5px;
            margin: 10px 0;
        }

        button:hover {
            background-color: #d43f00;
        }

        .baby-photo {
            width: 100%;
            max-width: 250px;
            border-radius: 10px;
            margin: 10px 0;
        }

        iframe {
            margin-top: 10px;
            border-radius: 10px;
        }

        form {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }

        input, select {
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }

        .hidden {
            display: none;
        }
    </style>

</body>
</html>
