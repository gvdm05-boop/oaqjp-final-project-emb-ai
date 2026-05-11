import requests

def emotion_detector(text_to_analyze):
    # The URL and Headers provided in your assignment screenshot
    url = 'https://sn-watson-emotion.labs.skills.network/v1/watson.runtime.nlp.v1/NlpService/EmotionPredict'
    header = {"grpc-metadata-mm-model-id": "emotion_aggregated-workflow_lang_en_stock"}
    
    # The input JSON format using the variable text_to_analyze
    myobj = { "raw_document": { "text": text_to_analyze } }
    
    # Sending the POST request
    response = requests.post(url, json=myobj, headers=header)
    
    # Returning the .text attribute specifically as requested in Task 2
    return response.text