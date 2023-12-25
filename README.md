# RESTful-API-Server
Flask server implementing a RESTful API with routes for CRUD operations.
from flask import Flask, request, jsonify

app = Flask(__name__)

data = []

@app.route('/api/data', methods=['GET'])
def get_data():
    return jsonify(data)

@app.route('/api/data', methods=['POST'])
def add_data():
    new_data = request.json
    data.append(new_data)
    return jsonify({'message': 'Data added successfully'})

# Implement PUT, DELETE routes for full CRUD functionality

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=80)
