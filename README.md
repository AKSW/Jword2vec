# Word2Vec RESTful Web Service
A service for code.google.com/p/word2vec models.

##Requirements

### local installation
Java 8, Maven 3

This step is done by the application now!
(Download and unzip to the 'data' folder: https://drive.google.com/file/d/0B7XkCwpI5KDYNlNUTTlSS21pQmM/edit)

Add your own api key in 'config/cfg.properties'.
Execute 'run.sh' to compile and start the application.

### online web service
An api key (if you don't have an api key, ask the autor for one).

## demo URI
http://139.18.2.164:4441

## Path
word2vec/distance

### parameter (GET method)
Parameter 'a' with a word, 'n' for the best n words (max 100) and the api key 'apikey'.

### example
http://139.18.2.164:4441/word2vec/distance?a=cat&n=10&apikey=your_api_key

### response
if word is known
```JSON
{
  "feline": 0.732623427803972,
  "kitten": 0.7464984522340501,
  "cats": 0.8099379097014889,
  "puppy": 0.7075453811739294,
  "beagle": 0.7150584059888843,
  "cat": 1.0000000409335996,
  "felines": 0.6755931328009979,
  "pup": 0.6934290769272593,
  "dog": 0.7609457255671259,
  "pet": 0.6891531532649253
}
```

## Path
word2vec/similarity

### parameter (GET method)
Parameter 'a' and 'b' with the words to compare and the api key 'apikey.

### response
if words are known
```javascript
{
  "a" : {
    "word": "String of the given word (a paramter)",
    "vec": [<300 dim vec for the given word>]
  },
  "b" : {
    "word": "String of the given word (b parameter)",
    "vec": [<300 dim vec for the given word>]
  },
  "cos": double value of cosine similarity
}
```
if one word is unknown, the value of this word is empty and the property 'vec' is not set.

### example
http://139.18.2.164:4441/word2vec/similarity?a=marry&b=wed&apikey=your_api_key

```JSON
{  
   "a":{  
      "vec":[  
         -0.12060547, -0.18847656, -0.31640625, 0.265625, -0.08105469, 0.14355469, 0.15917969, -0.29492188, 0.022094727, 0.107910156, 0.064941406, -0.041992188, -0.5234375, 0.20019531, -0.03491211, 0.125, 0.2734375, 0.061279297, -0.21679688, -0.10107422, -0.01965332, -0.015991211, 0.40234375, -0.15234375, 0.22558594, -0.17773438, -0.16210938, 0.020507812, -0.032226562, -0.19140625, 0.2265625, 0.1640625, -0.13085938, 0.028076172, -0.2109375, -0.12695312, 0.36328125, 0.017089844, -0.072265625, 0.27539062, 0.0040893555, 0.36132812, 0.35546875, -0.19921875, 0.07421875, -0.14746094, -0.21289062, -0.088378906, -0.18847656, 0.34179688, 0.010437012, -0.027954102, 0.064453125, -0.114746094, -0.1796875, -0.29882812, -0.34765625, -0.31445312, -0.3359375, -0.13867188, 0.5390625, -0.2421875, -0.048828125, 0.2890625, -0.36328125, 0.16601562, 0.00982666, 0.044677734, 0.19238281, 0.28515625, -0.076660156, 0.18261719, -0.041259766, 0.22070312, -0.006866455, 0.16992188, -0.359375, 0.044189453, 0.20703125, 0.39648438, -0.08935547, 0.26367188, -0.029907227, 0.25976562, 0.09375, 0.005279541, 0.1796875, 0.021240234, 0.2109375, 0.064941406, 0.09423828, -0.037597656, -0.36914062, 0.016235352, 0.12792969, 0.06738281, 0.29101562, -0.12890625, 0.056396484, -0.0018920898, -0.31835938, -0.122558594, 0.24023438, 0.002319336, 0.24414062, -0.45507812, -0.036132812, 0.03930664, -0.083496094, 0.12792969, 0.07861328, 0.010253906, 0.07861328, 0.011413574, 0.21777344, -0.29492188, 0.2890625, -0.068359375, 0.17578125, -0.041503906, 0.26953125, 0.24902344, 0.033935547, 0.24316406, 0.13964844, -0.48632812, 0.12597656, -0.04272461, -0.10644531, 0.023925781, 0.0046691895, 0.076171875, -0.04272461, 0.13476562, 0.23828125, 0.103027344, -0.037353516, 0.08886719, 0.13085938, 0.033447266, -0.103027344, 0.033203125, -0.296875, 0.1484375, -0.18652344, 0.08496094, -0.052978516, 0.01574707, -0.14160156, -0.08251953, 0.30859375, -0.0234375, 0.037597656, -0.034179688, -0.16796875, -0.23242188, -0.23144531, -0.31640625, 0.23144531, -0.48242188, -0.18457031, 0.078125, 0.34375, 0.15722656, -0.17773438, -0.46679688, 0.40429688, -0.14941406, -0.34570312, 0.04296875, -0.25976562, -0.3515625, -0.06298828, -0.068359375, 0.10595703, 0.0703125, 0.4140625, 0.10205078, -0.11767578, -0.08496094, -0.27148438, -0.21191406, -0.037109375, -0.091796875, 0.33203125, -0.12158203, -0.05834961, -0.026611328, 0.110839844, 0.122558594, 0.30664062, 0.1015625, 0.012634277, 0.3515625, 0.4375, 0.40820312, 0.06982422, 0.01965332, -0.09033203, 0.032958984, -0.11621094, 0.08886719, -0.018066406, -0.12695312, -0.13769531, 0.035888672, 0.06298828, 0.20703125, 0.21582031, -0.1640625, -0.19238281, 0.2890625, 0.31445312, -0.21972656, -0.07128906, -0.10205078, 0.12011719, 0.057861328, 0.20605469, 0.11035156, -0.15429688, 0.006958008, 0.27539062, -0.059570312, 0.28320312, -0.20019531, 0.1796875, -0.056152344, -0.21484375, 0.053955078, 0.13671875, -0.115722656, -0.14746094, -0.099609375, 0.41992188, 0.057617188, -0.359375, -0.30664062, -0.20117188, 0.24414062, -0.29492188, 0.09082031, 0.032958984, 0.25, 0.06738281, -0.08300781, -0.016113281, -0.25585938, 0.026733398, -0.087402344, 0.09765625, 0.19726562, 0.07324219, 0.19238281, 0.12207031, 0.103515625, -0.140625, -0.14941406, -0.05102539, 0.0119018555, 0.07763672, -0.27734375, -0.09716797, 0.06738281, 0.15820312, 0.078125, -0.24609375, -0.12792969, 0.048583984, 0.080566406, 0.13867188, 0.03100586, -0.19726562, 0.15917969, 0.16601562, -0.16503906, -0.26171875, -0.08203125, -0.2578125, -0.08203125, 0.15722656, -0.19824219, -0.0023345947, -0.001701355, 0.27539062, -0.029296875, 0.0013961792, -0.26171875, -0.087402344, 0.23242188, 0.3046875, 0.36914062, -0.3984375, -0.11328125, 0.07373047, 0.33007812, 0.009216309, -0.06640625, 0.3046875, 0.10107422
      ],
      "word":"marry"
   },
   "b":{  
      "vec":[  
         -0.1796875, -0.07763672, -0.55078125, 0.18066406, -0.17285156, 0.025024414, 0.03564453, -0.5078125, -0.0071105957, 0.016601562, 0.09326172, -0.06738281, -0.51171875, 0.27734375, 0.0027770996, 0.15234375, 0.30664062, 0.34375, -0.068359375, 0.045410156, -0.02746582, 0.03100586, 0.042236328, -0.21386719, 0.41015625, -0.20117188, -0.025634766, -0.09716797, -0.24902344, -0.33007812, 0.13671875, 0.0859375, -0.17871094, -0.13574219, -0.12792969, -0.13476562, 0.32226562, 0.0390625, -0.14160156, 0.28710938, -0.12988281, 0.016601562, 0.29492188, -0.19335938, 0.15429688, -0.06591797, -0.296875, 0.1171875, -0.021240234, 0.52734375, 0.13085938, -0.047607422, 0.107910156, -0.11425781, -0.048828125, -0.25390625, -0.49609375, -0.44921875, -0.32226562, -0.13671875, 0.4140625, -0.13085938, -0.01965332, 0.07910156, -0.45703125, 0.2734375, -0.087402344, -0.10546875, 0.09667969, 0.018432617, -0.038085938, 0.051513672, -0.140625, 0.30273438, -0.23632812, 0.27734375, -0.23339844, -0.045166016, -0.34960938, 0.31835938, -0.009277344, 0.021728516, 0.0043029785, 0.34765625, 0.17480469, -0.13867188, -0.012634277, 0.091308594, 0.15234375, 0.045410156, 0.13378906, -0.17871094, -0.27539062, 0.1015625, -0.0033721924, 0.17578125, -0.04248047, -0.22265625, -0.079589844, -0.041748047, -0.15136719, 0.029907227, 0.28710938, -0.027832031, 0.3359375, -0.38085938, 0.0072021484, 0.051757812, 0.03173828, 0.051757812, 0.22851562, 0.40625, 0.22558594, 0.017822266, 0.15234375, -0.23535156, 0.27929688, -0.09375, 0.3203125, -0.12695312, 0.453125, 0.17382812, 0.20800781, 0.06933594, 0.35546875, -0.44335938, 0.18554688, -0.24414062, -0.18164062, 0.096191406, 0.056152344, 0.012023926, 0.25976562, 0.109375, 0.27929688, 0.20507812, -0.13574219, 0.09814453, 0.14648438, 0.18261719, -0.41796875, 0.064941406, -0.122558594, -0.01928711, -0.19921875, 0.12988281, -0.16308594, 0.123046875, -0.016357422, -0.050048828, 0.36523438, -0.10058594, -0.018432617, -0.20898438, 0.017089844, -0.19335938, -0.29296875, -0.46875, 0.29882812, -0.421875, -0.110839844, 0.29882812, 0.55859375, -0.072265625, -0.37695312, -0.44335938, 0.20410156, 0.033203125, -0.41992188, 0.15332031, -0.36914062, -0.46289062, -0.046875, 0.076660156, 0.07421875, 0.40625, 0.40234375, 0.13769531, -0.059326172, -0.103515625, -0.30078125, 0.052246094, 0.12988281, -0.13867188, 0.48632812, -0.11230469, 0.064941406, 0.004058838, 0.037109375, 0.087402344, 0.33984375, 0.26953125, -0.19726562, 0.32226562, 0.17480469, 0.5859375, 0.083496094, 0.25, -0.14746094, 0.12890625, 0.16503906, 0.026245117, 0.07714844, -0.08251953, 0.056152344, 0.021606445, 0.27539062, 0.19238281, 0.083496094, -0.16503906, -0.30078125, 0.39648438, 0.46875, -0.15234375, 0.005493164, -0.19824219, 0.1796875, -0.024291992, 0.23046875, 0.2578125, 0.039794922, -0.010070801, 0.10644531, 0.03881836, 0.23730469, -0.20996094, 0.14160156, 0.21972656, -0.22851562, 0.076171875, -0.11230469, -0.041259766, -0.0072021484, -0.26757812, 0.45703125, 0.26953125, -0.15917969, -0.33789062, -0.171875, 0.3203125, -0.25976562, 0.12890625, 0.008361816, 0.096191406, -0.055664062, 0.04321289, -0.115722656, -0.1328125, 0.23535156, -0.27929688, 0.010620117, 0.10546875, 0.10595703, 0.09423828, 0.018432617, 0.2109375, 0.013427734, -0.17871094, -0.19628906, 0.0077209473, -0.28515625, -0.17675781, 0.15722656, -0.14941406, 0.17285156, 0.115234375, -0.1328125, -0.032226562, -0.012023926, 0.1171875, 0.14746094, -0.06298828, -0.30273438, 0.20410156, 0.05810547, 0.034423828, -0.12158203, 0.21484375, -0.3359375, -0.021606445, -0.035888672, -0.017089844, 0.01928711, -0.037841797, 0.46289062, -0.25195312, -0.20410156, -0.28710938, -0.08984375, 0.25, 0.43359375, 0.14648438, -0.40429688, -0.044921875, 0.125, 0.13378906, -0.06640625, -0.06591797, 0.19824219, 0.09082031
      ],
      "word":"wed"
   },
   "cos":0.7922742673001496
}
```

## Path
word2vec/vector

### parameter (GET method)
Parameter 'a' and 'apikey' with the api key.

### response
if words are known
```javascript
{
  "a" : {
    "word": "String of the given word (a paramter)",
    "vec": [<300 dim vec for the given word>]
  }
}
```
if the word is unknown, the value of this word is empty and the property 'vec' is not set.
