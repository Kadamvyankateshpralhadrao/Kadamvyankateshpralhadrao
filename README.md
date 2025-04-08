<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Ajay Fitness Club</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f4f4f4; }
    header { background: #1e1e1e; color: white; padding: 20px; text-align: center; }
    .container { max-width: 800px; margin: 30px auto; background: white; padding: 30px; box-shadow: 0 0 10px rgba(0,0,0,0.1); border-radius: 10px; }
    h2 { color: #333; }
    label { display: block; margin-top: 15px; }
    input { width: 100%; padding: 10px; margin-top: 5px; border-radius: 5px; border: 1px solid #ccc; }
    button { margin-top: 20px; padding: 10px 20px; background: #27ae60; color: white; border: none; border-radius: 5px; cursor: pointer; }
    button:hover { background: #219150; }
    .members { margin-top: 30px; }
    .member-entry { background: #eafaf1; padding: 10px; margin-bottom: 10px; border-radius: 5px; }
    footer { text-align: center; padding: 20px; color: #888; font-size: 14px; background: #f9f9f9; font-weight: bold; }
  </style>
</head>
<body>  <header>
    <h1>Ajay Fitness Club</h1>
  </header>  <div class="container">
    <h2>Member Registration</h2>
    <form id="memberForm">
      <label for="name">Member Name:</label>
      <input type="text" id="name" required /><label for="contact">Contact Number:</label>
  <input type="text" id="contact" required />

  <label for="start">Membership Start Date:</label>
  <input type="date" id="start" required />

  <label for="end">Membership End Date:</label>
  <input type="date" id="end" required />

  <button type="submit">Add Member</button>
</form>

<div class="members" id="memberList"></div>

  </div>  <footer>
    DIRECTED BY VYANKATESH KADAM
  </footer>  <script>
    const memberForm = document.getElementById('memberForm');
    const memberList = document.getElementById('memberList');
    const messageTemplate = `
नमस्कार!

Ajay Fitness Club मधील आपल्या सहवासासाठी मनःपूर्वक आभार.
आपली सदस्यता संपलेली आहे किंवा लवकरच संपणार आहे – म्हणूनच हा एक विशेष स्नेहपूर्वक संदेश.

आपल्या शरीरावर केलेली गुंतवणूक ही सर्वात मौल्यवान असते, आणि ती सातत्याने घडवण्याची गरज असते.

आजवर आपण आमच्या बरोबर प्रवास केला, हे आमच्यासाठी अभिमानास्पद आहे.
जर आपण पुन्हा आपल्या फिटनेस प्रवासाला एक नवी दिशा देऊ इच्छित असाल, तर आमचं दार सदैव आपल्या स्वागतासाठी उघडं आहे.

Ajay Fitness Club मध्ये आपणास लाभतील:

- प्रोफेशनल ट्रेनिंग व वैयक्तिक मार्गदर्शन
- हाय स्टँडर्ड फॅसिलिटीज व क्लासिक जिम वातावरण
- प्रत्येक महिन्याला मिळणारी नवी प्रेरणा व ट्रान्सफॉर्मेशनचा आत्मविश्वास

आपण ठरवलं, तर शरीर घडणं हे शक्यच आहे – आणि आम्ही त्यासाठी तुमच्या पाठीशी खंबीरपणे उभे आहोत.

"एक पाऊल पुन्हा... आणि प्रवास अजून भव्य होणार!"
आमच्या सोबत पुन्हा एकदा तुमचं स्वागत करण्यास आम्ही आतुर आहोत.

Ajay Fitness Club – जिथे फिटनेस हा फक्त व्यायाम नसून, एक लाईफस्टाइल आहे.`;

    memberForm.addEventListener('submit', function(e) {
      e.preventDefault();
      const name = document.getElementById('name').value;
      const contact = document.getElementById('contact').value;
      const start = document.getElementById('start').value;
      const end = document.getElementById('end').value;

      const endDate = new Date(end);
      const today = new Date();
      const twoDaysBeforeEnd = new Date(endDate);
      twoDaysBeforeEnd.setDate(endDate.getDate() - 2);

      let msg = '';
      if (today.toDateString() === twoDaysBeforeEnd.toDateString()) {
        msg = `<strong>WhatsApp Message:</strong><br><pre>${messageTemplate}</pre>`;}

  const memberHTML = `
    <div class="member-entry">
      <strong>Name:</strong> ${name} <br>
      <strong>Contact:</strong> ${contact} <br>
      <strong>Start:</strong> ${start} <br>
      <strong>End:</strong> ${end} <br>
      ${msg}
    </div>
  `;
  memberList.innerHTML += memberHTML;
  memberForm.reset();
});

  </script></body>
</html>
