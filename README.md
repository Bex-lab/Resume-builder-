# Resume-builder-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Resume Builder</title>
    <style>
        /* Add some basic styling */
        body { font-family: Arial, sans-serif; max-width: 600px; margin: 0 auto; padding: 20px; }
        input, textarea { width: 100%; margin-bottom: 10px; }
        button { background-color: #4CAF50; color: white; padding: 10px 20px; border: none; cursor: pointer; }
    </style>
</head>
<body>
    <h1>Resume Builder</h1>
    <form id="resumeForm">
        <input type="text" id="name" placeholder="Full Name" required>
        <input type="email" id="email" placeholder="Email" required>
        <input type="tel" id="phone" placeholder="Phone" required>
        <textarea id="summary" placeholder="Professional Summary" required></textarea>
        <textarea id="skills" placeholder="Skills (comma-separated)" required></textarea>
        <textarea id="experience" placeholder="Work Experience" required></textarea>
        <textarea id="education" placeholder="Education" required></textarea>
        <button type="submit">Create Resume</button>
    </form>
    <div id="output"></div>

    <script>
        document.getElementById('resumeForm').onsubmit = function(e) {
            e.preventDefault();
            var resume = {
                name: document.getElementById('name').value,
                email: document.getElementById('email').value,
                phone: document.getElementById('phone').value,
                summary: document.getElementById('summary').value,
                skills: document.getElementById('skills').value.split(',').map(skill => skill.trim()),
                experience: document.getElementById('experience').value,
                education: document.getElementById('education').value
            };
            
            var output = document.getElementById('output');
            output.innerHTML = `
                <h2>Resume</h2>
                <p><strong>Name:</strong> ${resume.name}</p>
                <p><strong>Email:</strong> ${resume.email}</p>
                <p><strong>Phone:</strong> ${resume.phone}</p>
                <p><strong>Summary:</strong> ${resume.summary}</p>
                <p><strong>Skills:</strong> ${resume.skills.join(', ')}</p>
                <p><strong>Experience:</strong> ${resume.experience}</p>
                <p><strong>Education:</strong> ${resume.education}</p>
            `;
        };
    </script>
</body>
</html>
