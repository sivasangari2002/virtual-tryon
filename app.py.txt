from flask import Flask, request, send_file
from flask_cors import CORS

app = Flask(__name__)
CORS(app)

@app.route('/tryon', methods=['POST'])
def tryon():
    person = request.files['person']
    garment = request.files['garment']
    person.save("person.png")
    garment.save("garment.png")
    return send_file("garment.png", mimetype='image/png')
