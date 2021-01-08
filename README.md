# Nepali poem generation using char RNN in Keras


This project generates the nepali poem using the char RNN. Although any sequence like music,other language text can be generated with this architecture. 


## Tools used
Google colab for training 
python (3.6)
tensorflow (2.0.0)
keras (2.3.1)


## Data Preparation
The data is divided into two parts X(text encoding) and Y(target).

X  = (BATCH_SIZE, SEQ_LENGTH) of dimension (16,64).Here SEQ_LENGTH is the time_step for LSTM

Y = (BATCH_SIZE, SEQ_LENGTH, vocab_size) of dimension(16,64,73)
    . Here vocab size is the total number of unique alphabets in the dataset. vocab_size is the one_hot of 73 dims vector which our model has to predict.

![Data preparation pic](/img/data_prep.png)

## Training
For training use following command

```bash
$ python train.py --input input.txt --epochs 500 --freq 100
```
Here freq refers to saving models after particular number of epochs. Epochs, input data and freq can be changed as you like.

The training is done for 500 epochs only and accuracy achevied was 84.4%
![accuracy graph](/img/accuracy.png)

## For prediction
For prediction use following command
```bash
$ python sample.py 500 --len 500 
```
Here 500 is for model epoch number which have been trained and placed inside model folder. --len refers to the number of alphabets to produce by model.

## Output sample

प्चारमा फुली घुम्दै  झुल्दछन् ।
फर्केको बिटाएँ ।
एक बिन्दुमा गोली !
गोली हो यो गोली हो !
तिनका मर्लान्,
असिना पर्लान्, पग्ली झर्लान्
ह्लासाको मर्यो अनुर सुनका छाना रङ्ग फैँछन् भ्यालो नेपाली
यो सिन्दो र मोरी !
मानव–प्रखण्ड शार् ?
बुझ्दछ कलिमा, प्रसिता, प्रलयो !
अरङ्गले प्रथम शहर ?
स्नान गरा अर पृथिवी पुरुषको मुख रेशमी !
रातको मन्त्र हुन्छे बास्नी ।
हाम्रा जान् आँखा रङ्ग उचाली,
एक शान्ति किन ? साँझमा मूज्र ले सुनौला !
मिल्ना गर्छ मौर्छयो मनको जलले विवाल !
दादधको ज्याति नै बलि !
रोइनँ रोइरस् ! लौ आ

## Conclusion
The output of this model not remarkable but it is surely good starting for begineers. This project is not only limited to poem generation, we can even generate various text and even music from this architecture.

# Reference
https://github.com/ekzhang/char-rnn-keras 
