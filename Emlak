from flask import Flask, render_template_string, request, redirect

app = Flask(__name__)

customers = []
properties = []

@app.route("/")
def home():
    return """
    <h1>🏢 Reyhanoğlu Emlak CRM</h1>
    <a href='/customers'>Müşteriler</a><br>
    <a href='/properties'>Portföy</a><br>
    <a href='/add_customer'>Müşteri Ekle</a><br>
    <a href='/add_property'>İlan Ekle</a><br>
    """

@app.route("/customers")
def customers_page():
    html = "<h2>Müşteriler</h2>"
    for c in customers:
        html += f"<p>{c}</p>"
    return html

@app.route("/add_customer", methods=["GET","POST"])
def add_customer():
    if request.method == "POST":
        customers.append(request.form["name"])
        return redirect("/customers")
    return "<form method='post'>Ad: <input name='name'><button>Kaydet</button></form>"

@app.route("/properties")
def properties_page():
    html = "<h2>Portföy</h2>"
    for p in properties:
        html += f"<p>{p}</p>"
    return html

@app.route("/add_property", methods=["GET","POST"])
def add_property():
    if request.method == "POST":
        properties.append(request.form["title"])
        return redirect("/properties")
    return "<form method='post'>Başlık: <input name='title'><button>Kaydet</button></form>"

if __name__ == "__main__":
    app.run()
