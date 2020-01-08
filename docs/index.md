# Welcome to Project ReSeed 
By : 
   Hari pranav .A . 

   Ashwin M S

   Amogh M Aradhya

   Pradhyumna Rahul


<br>


##Main Causes of Farmer suicides in India

<br>

1. High Rate of Intrest on Loans for purchase of the crop
 
2. High Interests rates on loans cripple the farmer. 

3. Inflation

4. Volatile prices of daily commodity tends to impact households.

5. GMO/Pesticides

6. Highly Artificial and Unnatural practices are adopted in hope of better profits.

<br>
## Solution
<br>

 A have a platform that connects the consumer directly to the farmer.

 An IOT device for <b>real time crop health monitoring</b> which ensures that the crop is grown in the best manner possible free of excess pesticides .


<br>

 <b>This ensures that</b> :
<br>

1. The consumer ends up paying the actual price for the crop quoted by the farmer rather than the price in the market.

2. The farmer need not take loans , as they are funded by the consumers itself.

3. Real Time Crop Health Monitoring On A Distributed Ledger ensures that we can use analytics to diversify the Crops grown by the Farmers 

<br>
<br>



## Hardware Used


###1. Maintenancefree UPS/Inverter Battery 

![Battery](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/Battery.jpg) 

###2. Robocraze Dht11 Temperature and Humidity Sensor Module

![Humidity and Temperature Sensor](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/DHT11.jpg)

###3. 12V 6W PV Polycrystalline Solar Panel

![Solar Panel](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/SolarPanel.jpg)

###4. 10A 20A amp Solar USB Charge Controller Regulator 

![10A 20A amp Solar USB Charge Controller Regulator](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/SolarCharge.jpg)

###5. Complete Set Up
![Complete Set Up](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/FullPic.jpeg)

## Code to Send the Data to Firebase

        #include <DHT.h>  // Including library for dht
        #include <ESP8266WiFi.h>
        #include <ESP8266HTTPClient.h>

        const char* host = "secret-savannah-46302.herokuapp.com";
        
        
        const char *ssid =  "";     // replace with your wifi ssid and wpa2 key
        const char pass =  "";     //password
        const char server = "https://secret-savannah-46302.herokuapp.com/";

        #define DHTPIN 0          //pin where the dht11 is connected

        DHT dht(DHTPIN, DHT11);

        WiFiClient client;

        void setup()
        {
          Serial.begin(115200);
          delay(10);
          dht.begin();

          Serial.println("Connecting to ");
          Serial.println(ssid);


          WiFi.begin(ssid, pass);

          while (WiFi.status() != WL_CONNECTED)
          {
            delay(500);
            Serial.print(".");
          }
          Serial.println("");
          Serial.println("WiFi connected");

        }

        void loop()
        {
          Serial.print("connecting to ");
          Serial.println(host);

          WiFiClient client;
          const int httpPort = 80;
          if (!client.connect(host, httpPort)) {
            Serial.println("connection failed");
            return;
          }

          String url = "/addData?H=69&M=16&T=99";
          Serial.print("Requesting URL: ");
          Serial.println(url);

          client.print(String("GET ") + url + " HTTP/1.1\r\n" +
                       "Host: " + host + "\r\n" + 
                       "Content-Type: application/x-www-form-urlencoded\r\n" +
                       "Content-Length : 23\r\n" +
                       "Connection: keep-alive\r\n\r\n");
          delay(500);

          while(client.available()){
            String line = client.readStringUntil('\r');
            Serial.print(line);
          }

          Serial.println();
          Serial.println("closing connection");
          delay(3000);

        }



## Paper Presentation 


Introduction :

Abstract: 


1.A peer to peer platform that connects the farmers and the end consumers with the integration of IOT,ML and Blockchain to track the production of crop growth from the time of seed plantaiton to the harvest.

2.The main use of the sensors are to give real time data about the crop such as temperature , humidity and the pH level of the crop.

3.Periodically the data is agregated and is pushed into the blockchain to guarentee the trail of data .

4.ML is used to identify the disease of the crop when the farmer clicks the pictures and sends the picture to the platform.

5.This finally ensures that the farmer is connected to the consumer and that the transfer of funds happen on 
the platform.


Keywords: ML,IOT,BLOCKCHAIN,DISTRIBUTED LEDGER.

Introduction:

  The main causes of farmer suicide in india are :


    The surge in input costs:
            A major cause of the farmers’ suicides in India has been the increasing burden on the farmers due to inflated prices of agricultural inputs. 
    
    Cost of chemicals and seeds: 
            Be it the fertilisers, crop protection chemicals or even the seeds for cultivation, farming has become expensive for the already indebted farmers.
        
    Costs of Agricultural equipment:  
          The input costs, moreover, aren’t limited to the basic raw materials. Using agricultural equipment and machinery like tractors, submersible pumps etc adds to the already surging costs. Besides, these secondary inputs have themselves become less affordable for the small and marginal farmers.

    Labour costs: 
      Likewise, hiring labourers and animals is getting costlier too. While this may reflect an improvement in the socio-economic status of the labourers, driven primarily by MGNERGA and hike in minimum basic income, this has not gone too well with boosting the agriculture sector.

    Distressed due to loans:
        NCRB data points out that in 2474 suicides out of the studied 3000 farmer suicides in 2015 the victims had unpaid loans from local banks. This is clear enough an indication for drawing correlations between the two. 

    Lack of direct integration with the market:
       Although initiatives like the National Agricultural Market and contract farming are helping integrate the farmers’ produce directly with the market, cutting the role of intermediaries, the reality is still lagging behind.

    Lack of awareness: 
      The digital divide, as well as the literacy gap, has made the marginal and small farmers particularly vulnerable due to their inability to utilise the positives of government policies. 

    Water crisis:
       The concentration of these suicides in the water-deficit regions of states like Maharashtra, Karnataka is a manifestation of how the water crisis and thereby failure to meet production demands have intensified the menace. 
        
    

# IOT and Hardware:


## Hardware Used


###1. Maintenancefree UPS/Inverter Battery 

![Battery](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/Battery.jpg) 

###2. Robocraze Dht11 Temperature and Humidity Sensor Module

![Humidity and Temperature Sensor](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/DHT11.jpg)

###3. 12V 6W PV Polycrystalline Solar Panel

![Solar Panel](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/SolarPanel.jpg)

###4. 10A 20A amp Solar USB Charge Controller Regulator 

![10A 20A amp Solar USB Charge Controller Regulator](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/SolarCharge.jpg)

###5. Complete Set Up
![Complete Set Up](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/FullPic.jpeg)


## Code to Send the Data to Firebase

        #include <DHT.h>  // Including library for dht
        #include <ESP8266WiFi.h>
        #include <ESP8266HTTPClient.h>

        const char* host = "secret-savannah-46302.herokuapp.com";
        
        
        const char *ssid =  "";     // replace with your wifi ssid and wpa2 key
        const char pass =  "";     //password
        const char server = "https://secret-savannah-46302.herokuapp.com/";

        #define DHTPIN 0          //pin where the dht11 is connected

        DHT dht(DHTPIN, DHT11);

        WiFiClient client;

        void setup()
        {
          Serial.begin(115200);
          delay(10);
          dht.begin();

          Serial.println("Connecting to ");
          Serial.println(ssid);


          WiFi.begin(ssid, pass);

          while (WiFi.status() != WL_CONNECTED)
          {
            delay(500);
            Serial.print(".");
          }
          Serial.println("");
          Serial.println("WiFi connected");

        }

        void loop()
        {
          Serial.print("connecting to ");
          Serial.println(host);

          WiFiClient client;
          const int httpPort = 80;
          if (!client.connect(host, httpPort)) {
            Serial.println("connection failed");
            return;
          }

          String url = "/addData?H=69&M=16&T=99";
          Serial.print("Requesting URL: ");
          Serial.println(url);

          client.print(String("GET ") + url + " HTTP/1.1\r\n" +
                       "Host: " + host + "\r\n" + 
                       "Content-Type: application/x-www-form-urlencoded\r\n" +
                       "Content-Length : 23\r\n" +
                       "Connection: keep-alive\r\n\r\n");
          delay(500);

          while(client.available()){
            String line = client.readStringUntil('\r');
            Serial.print(line);
          }

          Serial.println();
          Serial.println("closing connection");
          delay(3000);

        }


#Product Concept 

![Full Pic](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/FullPic.jpeg)


###1. The Solar Panel Powers the Battery
###2. The Batter powers the charge controller
###3. The charge controller powers the Node MCU
###4. The Node MCU sends the data from DHT11(Temperature and Humidity) 

###5. Sensor ,and the Soil Moisture Sensor to Heroku . 
###6. Heroku is an interface between Node and the Database for security .

## UML Diagram
![UML](https://raw.githubusercontent.com/HariPranav/TeamReseedComponents/master/Reseed/UML.png)

## ML to detect the plant disease


 Model: Google Inception 2.0 (Pre-trained model fine tuned)


 Method:

    Read camera feed
    Extract frame and store temporarily


![step2](https://raw.githubusercontent.com/1nF0rmed/plantDiseaseDetectorFlask/master/step2.png)



    Send frame to REST API server

![step3](https://raw.githubusercontent.com/1nF0rmed/plantDiseaseDetectorFlask/master/step3.png)




    Server processed image and inputs to Tensorflow Model


![step4](https://raw.githubusercontent.com/1nF0rmed/plantDiseaseDetectorFlask/master/step4.png)

  

    Tensorflow Model provides predicted classification

![step5](https://raw.githubusercontent.com/1nF0rmed/plantDiseaseDetectorFlask/master/step5.png)



The plant state is then set to the classification

![step6](https://raw.githubusercontent.com/1nF0rmed/plantDiseaseDetectorFlask/master/output.png)



# main.py 

  
  
  
  
  
  
  
  
  from flask import Flask, flash, redirect, url_for, request
  from werkzeug.utils import secure_filename
  import tensorflow as tf
  import numpy as np
  import uuid
  import os


  UPLOAD_FOLDER = './tmp_files/'
  ALLOWED_EXTENSIONS = set(['png', 'jpg', 'jpeg'])
  app = Flask(__name__)
  app.config['UPLOAD_FOLDER'] = UPLOAD_FOLDER

  state = "unknown"

  _graph = None
  _labels = None
  model = None

  def load_graph(model_file):
      graph = tf.Graph()
      graph_def = tf.GraphDef()

      with open(model_file, "rb") as f:
          graph_def.ParseFromString(f.read())

      with graph.as_default():
          tf.import_graph_def(graph_def)

      return graph

  def load_labels(label_file):
      label = []
      proto_as_ascii_lines = tf.gfile.GFile(label_file).readlines()

      for l in proto_as_ascii_lines:
          label.append(l.rstrip())

      return label

  def read_tensor_from_image_file(file_name, input_height=224, input_width=224,
                                  input_mean=128, input_std=128):
      input_name = "file_reader"
      output_name = "normalized"
      file_reader = tf.read_file(file_name, input_name)
      if file_name.endswith(".png"):
          image_reader = tf.image.decode_png(file_reader, channels=3,
                                              name="png_reader")

      else:
          image_reader = tf.image.decode_jpeg(file_reader, channels=3,
                                              name="jpeg_reader")

      float_caster = tf.cast(image_reader, tf.float32)
      dims_expander = tf.expand_dims(float_caster, 0)
      resized = tf.image.resize_bilinear(dims_expander, [input_height, input_width])
      normalized = tf.divide(tf.subtract(resized, [input_mean]), [input_std])

      sess = tf.Session()
      result = sess.run(normalized)

      return result

  def loadModel(frozen_graph_filename, label_filename):
      global model

      # Load the tensorflow frozen graph and label files
      graph = load_graph(frozen_graph_filename)
      labels = load_labels(label_filename)

      return graph,labels

  def allowed_file(filename):
      return '.' in filename and \
              filename.rsplit('.', 1)[1].lower() in ALLOWED_EXTENSIONS

  def getPrediction(file_path):

      # Get the loaded graph and labels
      global _graph
      global _labels

      # Read tensor from image file
      t = read_tensor_from_image_file(file_path)

      input_name = "import/input"
      output_name = "import/final_result"
      input_operation = _graph.get_operation_by_name(input_name)
      output_operation = _graph.get_operation_by_name(output_name)

      # Start the tensorflow session to compute the graph
      with tf.Session(graph=_graph) as sess:
          results = sess.run(output_operation.outputs[0],
                              {input_operation.outputs[0]: t})

      results = np.squeeze(results)

      top_k = results.argsort()[-5:][::-1]

      return str("{}".format(_labels[top_k[0]]))

  @app.route('/api/v1/<name>')
  def success(name):
      return "welcome %s" % name

  def gen_random_filename(filename):
      # split extension and name
      b = filename.split(".")

      # Set name to a unique id
      b[0] = str(uuid.uuid4())

      # return the new filename
      return '.'.join(b)

  @app.route('/api/v1/setState', methods=['POST'])
  def setState():
      global state
      filename = ""

      # Get the file from the POST Request
      if 'file' not in request.files:
          print 'No file part'
          return redirect(request.url)

      _file = request.files['file']
      if _file and allowed_file(_file.filename):
          filename = gen_random_filename(_file.filename)
          _file.save(os.path.join(app.config['UPLOAD_FOLDER'], filename))

      # TODO Classify the image
      state =  getPrediction(os.path.join(app.config['UPLOAD_FOLDER'], filename))

      # TODO Set the state to the label

      return "Added"

  @app.route('/api/v1/getState', methods=['GET'])
  def getState():
      global state

      # TODO get the current state of the plant

      # TODO return the state of the plant
      return state

  if __name__ == "__main__":

      # Load the graph and labels
      global _graph
      global _labels

      graph_filename = "retrained_graph.pb"
      graph_labels = "retrained_labels.txt"

      _graph,_labels = loadModel(graph_filename, graph_labels)

      # print getPrediction("./test4.jpg")

      # Load the flask api
      app.run(host="0.0.0.0", port=5000)

  

## models.py
  <!-- Copyright 2017 The TensorFlow Authors. All Rights Reserved.

  Licensed under the Apache License, Version 2.0 (the "License");
  you may not use this file except in compliance with the License.
  You may obtain a copy of the License at

      http://www.apache.org/licenses/LICENSE-2.0

  Unless required by applicable law or agreed to in writing, software
  distributed under the License is distributed on an "AS IS" BASIS,
  WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
  See the License for the specific language governing permissions and
  limitations under the License.
  ============================================================================== -->

  from __future__ import absolute_import

  from __future__ import division

  from __future__ import print_function


  import argparse

  import sys

  import time

  import numpy as np
  import tensorflow as tf

  def load_graph(model_file):
    graph = tf.Graph()
    graph_def = tf.GraphDef()

    with open(model_file, "rb") as f:
      graph_def.ParseFromString(f.read())
    with graph.as_default():
      tf.import_graph_def(graph_def)

    return graph

  def read_tensor_from_image_file(file_name, input_height=299, input_width=299,input_mean=0, input_std=255):

    input_name = "file_reader"

    output_name = "normalized"

    file_reader = tf.read_file(file_name, input_name)

    if file_name.endswith(".png"):

      image_reader = tf.image.decode_png(file_reader, channels = 3,name='png_reader')

    elif file_name.endswith(".gif"):

      image_reader = tf.squeeze(tf.image.decode_gif(file_reader,name='gif_reader'))                                    

    elif file_name.endswith(".bmp"):

      image_reader = tf.image.decode_bmp(file_reader, name='bmp_reader')

    else:

      image_reader = tf.image.decode_jpeg(file_reader, channels = 3,name='jpeg_reader')
                                          
    float_caster = tf.cast(image_reader, tf.float32)

    dims_expander = tf.expand_dims(float_caster, 0);
    
    resized = tf.image.resize_bilinear(dims_expander, [input_height, input_width])

    normalized = tf.divide(tf.subtract(resized, [input_mean]), [input_std])

    sess = tf.Session()

    result = sess.run(normalized)


    return result

  def load_labels(label_file):
  
    label = []
    proto_as_ascii_lines = tf.gfile.GFile(label_file).readlines()
    for l in proto_as_ascii_lines:
      label.append(l.rstrip())
    return label

  if __name__ == "__main__":

    file_name = "tf_files/flower_photos/daisy/3475870145_685a19116d.jpg"
    model_file = "retrained_graph.pb"
    label_file = "retrained_labels.txt"
    input_height = 224
    input_width = 224
    input_mean = 128
    input_std = 128
    input_layer = "input"
    output_layer = "final_result"

    parser = argparse.ArgumentParser()
    parser.add_argument("--image", help="image to be processed")
    parser.add_argument("--graph", help="graph/model to be executed")
    parser.add_argument("--labels", help="name of file containing labels")
    parser.add_argument("--input_height", type=int, help="input height")
    parser.add_argument("--input_width", type=int, help="input width")
    parser.add_argument("--input_mean", type=int, help="input mean")
    parser.add_argument("--input_std", type=int, help="input std")
    parser.add_argument("--input_layer", help="name of input layer")
    parser.add_argument("--output_layer", help="name of output layer")
    args = parser.parse_args()

    if args.graph:
      model_file = args.graph
    if args.image:
      file_name = args.image
    if args.labels:
      label_file = args.labels
    if args.input_height:
      input_height = args.input_height
    if args.input_width:
      input_width = args.input_width
    if args.input_mean:
      input_mean = args.input_mean
    if args.input_std:
      input_std = args.input_std
    if args.input_layer:
      input_layer = args.input_layer
    if args.output_layer:
      output_layer = args.output_layer

    graph = load_graph(model_file)
    t = read_tensor_from_image_file(file_name,
                                    input_height=input_height,
                                    input_width=input_width,
                                    input_mean=input_mean,
                                    input_std=input_std)

    input_name = "import/" + input_layer
    output_name = "import/" + output_layer
    input_operation = graph.get_operation_by_name(input_name);
    output_operation = graph.get_operation_by_name(output_name);

    with tf.Session(graph=graph) as sess:
      start = time.time()
      results = sess.run(output_operation.outputs[0],
                        {input_operation.outputs[0]: t})
      end=time.time()
    results = np.squeeze(results)

    top_k = results.argsort()[-5:][::-1]
    labels = load_labels(label_file)

    print('\nEvaluation time (1-image): {:.3f}s\n'.format(end-start))
    template = "{} (score={:0.5f})"
    for i in top_k:
      print(template.format(labels[i], results[i]))
