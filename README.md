<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Insurance Claim Form</title>
    <style>
        body { font-family: Arial, sans-serif; margin: 20px; background-color: #f4f4f4; }
        form { background-color: #fff; padding: 30px; border-radius: 8px; box-shadow: 0 0 10px rgba(0, 0, 0, 0.1); max-width: 600px; margin: auto; }
        fieldset { border: 1px solid #ddd; padding: 20px; margin-bottom: 20px; border-radius: 5px; }
        legend { font-weight: bold; font-size: 1.2em; color: #333; padding: 0 10px; }
        div { margin-bottom: 15px; }
        label { display: block; margin-bottom: 5px; font-weight: bold; color: #555; }
        input[type="text"],
        input[type="email"],
        input[type="password"],
        input[type="tel"],
        input[type="date"],
        input[type="number"],
        input[type="url"],
        input[type="search"],
        textarea,
        select {
            width: calc(100% - 22px);
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            box-sizing: border-box;
            font-size: 1em;
        }
        input[type="radio"],
        input[type="checkbox"] {
            margin-right: 5px;
        }
        input[type="submit"],
        input[type="reset"] {
            background-color: #007bff;
            color: white;
            padding: 10px 20px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 1em;
            margin-right: 10px;
        }
        input[type="reset"] {
            background-color: #6c757d;
        }
        input[type="submit"]:hover,
        input[type="reset"]:hover {
            opacity: 0.9;
        }
        .radio-group, .checkbox-group {
            border: 1px solid #eee;
            padding: 10px;
            border-radius: 4px;
            background-color: #f9f9f9;
        }
        .radio-group label, .checkbox-group label {
            display: inline-block;
            margin-right: 15px;
            font-weight: normal;
        }
    </style>
</head>
<body>
    <h1>Insurance Claim Form</h1>

    <form action="/serverlogic" method="post" enctype="multipart/form-data">
        <fieldset>
            <legend>Personal Information</legend>

            <div>
                <label for="fullName">Full Name:</label>
                <input type="text" id="fullName" name="fullName" placeholder="Enter your full name" required autofocus>
            </div>

            <div>
                <label for="email">Email Address:</label>
                <input type="email" id="email" name="email" placeholder="your.email@example.com" required>
            </div>

            <div>
                <label for="password">Choose a Password:</label>
                <input type="password" id="password" name="password" minlength="8" maxlength="20" required placeholder="Min 8, Max 20 characters">
            </div>

            <div>
                <label for="phone">Phone Number:</label>
                <input type="tel" id="phone" name="phone" pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}" required placeholder="e.g., 123-456-7890">
                <small>Format: 123-456-7890</small>
            </div>

            <div>
                <label for="dob">Date of Birth:</label>
                <input type="date" id="dob" name="dob" required max="2025-07-23">
            </div>

            <div>
                <label for="age">Age:</label>
                <input type="number" id="age" name="age" min="18" max="100" required placeholder="Must be 18-100">
            </div>

            <div class="radio-group">
                <label>Gender:</label>
                <label for="genderMale"><input type="radio" id="genderMale" name="gender" value="male" required> Male</label>
                <label for="genderFemale"><input type="radio" id="genderFemale" name="gender" value="female"> Female</label>
                <label for="genderOther"><input type="radio" id="genderOther" name="gender" value="other"> Other</label>
            </div>
        </fieldset>

        <fieldset>
            <legend>Claim Details</legend>

            <div>
                <label for="claimType">Type of Claim:</label>
                <select id="claimType" name="claimType" required>
                    <option value="">--Please choose an option--</option>
                    <option value="auto">Auto Insurance Claim</option>
                    <option value="health">Health Insurance Claim</option>
                    <option value="home">Home Insurance Claim</option>
                    <option value="life">Life Insurance Claim</option>
                    <option value="travel">Travel Insurance Claim</option>
                </select>
            </div>

            <div>
                <label for="incidentDate">Date of Incident:</label>
                <input type="date" id="incidentDate" name="incidentDate" required max="2025-07-23">
            </div>

            <div>
                <label for="incidentDescription">Description of Incident:</label>
                <textarea id="incidentDescription" name="incidentDescription" rows="5" placeholder="Provide a detailed description of the incident leading to the claim." required></textarea>
            </div>

            <div class="checkbox-group">
                <label>Documents to Upload:</label>
                <div><label for="policeReport"><input type="checkbox" id="policeReport" name="documents[]" value="police_report"> Police Report</label></div>
                <div><label for="medicalBills"><input type="checkbox" id="medicalBills" name="documents[]" value="medical_bills"> Medical Bills</label></div>
                <div><label for="repairEstimates"><input type="checkbox" id="repairEstimates" name="documents[]" value="repair_estimates"> Repair Estimates</label></div>
                <div><label for="photos"><input type="checkbox" id="photos" name="documents[]" value="photos"> Photos of Damage</label></div>
                <div><label for="witnessStatements"><input type="checkbox" id="witnessStatements" name="documents[]" value="witness_statements"> Witness Statements</label></div>
            </div>

            <div>
                <label for="uploadFile">Upload Supporting Documents:</label>
                <input type="file" id="uploadFile" name="uploadFile" accept=".pdf, .doc, .docx, .jpg, .png" required>
            </div>
        </fieldset>

        <fieldset>
            <legend>Additional Information</legend>

            <div>
                <label for="website">Reference Website (if any):</label>
                <input type="url" id="website" name="website" placeholder="https://example.com">
            </div>

            <div>
                <label for="searchQuery">Search for related claims:</label>
                <input type="search" id="searchQuery" name="searchQuery" placeholder="Enter keywords for search">
            </div>

            <div>
                <label for="claimProgress">Claim Processing Progress:</label>
                <progress id="claimProgress" value="30" max="100">30%</progress>
            </div>
        </fieldset>

        <div>
            <input type="submit" value="Submit Claim">
            <input type="reset" value="Reset Form">
        </div>
    </form>
</body>
</html>
