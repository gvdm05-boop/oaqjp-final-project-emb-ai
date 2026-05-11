import requests
import json

def emotion_detector(text_to_analyze):
    # Step 1: Request data from the Watson NLP API
    url = 'https://sn-watson-emotion.labs.skills.network/v1/watson.runtime.nlp.v1/NlpService/EmotionPredict'
    header = {"grpc-metadata-mm-model-id": "emotion_aggregated-workflow_lang_en_stock"}
    myobj = {"raw_document": { "text": text_to_analyze } }
    response = requests.post(url, json=myobj, headers=header)
    
    # Step 2: Convert the response text into a dictionary using json library
    formatted_response = json.loads(response.text)
    
    # Step 3: Extract the required set of emotions
    # The scores are nested inside the first element of emotionPredictions
    emotions = formatted_response['emotionPredictions'][0]['emotion']
    
    # Step 4: Write the code logic to find the dominant emotion
    # This finds the emotion name (key) that has the highest score (value)
    dominant_emotion = max(emotions, key=emotions.get)
    
    # Step 5: Return the output in the format specified by the assignment
    return {
        'anger': emotions['anger'],
        'disgust': emotions['disgust'],
        'fear': emotions['fear'],
        'joy': emotions['joy'],
        'sadness': emotions['sadness'],
        'dominant_emotion': dominant_emotion
    }