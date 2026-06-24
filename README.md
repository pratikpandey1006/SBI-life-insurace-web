# SBI-life-insurace-web
[README.md](https://github.com/user-attachments/files/29277571/README.md)
# SBI-life-insurace-web
from flask import Flask, render_template_string, request

app = Flask(__name__)

html = """
<!DOCTYPE html>
<html>
<head>
<title>SBI Life Vehicle Insurance Service</title>
</head>

<body>

<h1>SBI Life Vehicle Insurance Service</h1>
<p>Get insurance assistance for your car or bike.</p>

<form method="POST">
Name:<Radha Raman Pandey>
<input type="text" name="name"><br><br>

Vehicle Number:<br>
<input type="text" name="vehicle"><br><br>

Mobile Number:<+91-9335269165>
<input type="text" name="mobile"><br><br>

<input type="submit" value="Submit">
</form>

</body>
</html>
"""

@app.route("/", methods=["GET", "POST"])
def home():
    if request.method == "POST":
        name = request.form["name"]
        vehicle = request.form["vehicle"]
        mobile = request.form["mobile"]

        print("New Lead:")
        print("Name:", name)
        print("Vehicle:", vehicle)
        print("Mobile:", mobile)

        return "Thank you! Our advisor will contact you soon."

    return render_template_string(html)

if __name__ == "__main__":
    app.run(debug=True)
