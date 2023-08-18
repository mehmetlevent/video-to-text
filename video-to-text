
import speech_recognition as sr

# Kodunuzun geri kalanı

import speech_recognition as sr
import moviepy.editor as mp

# Video dosyasının yolu
video_path = "\\video.avi"

# # Videoyu ses dosyasına dönüştürme
videoclip = mp.VideoFileClip(video_path)
audioclip = videoclip.audio
audioclip.write_audiofile("temp_audio.wav")

# # Ses dosyasını metne dönüştürme
recognizer = sr.Recognizer()
audio_file = sr.AudioFile("temp_audio.wav")

with audio_file as source:
    audio = recognizer.record(source)

text = recognizer.recognize_google(audio, language="tr-TR")  # Metni Türkçe olarak tanımlanmış dil modeli kullanarak dönüştürme
print(text)

# Altyazı dosyasını oluşturma
subtitle_path = "subtitle.srt"
subtitle_file = open(subtitle_path, "w")

# Altyazı içeriğini oluşturma
subtitle_content = "1\n00:00:00,000 --> 00:25:32,000\n" + text  # Örnek olarak, 5 saniyelik bir süre boyunca altyazı oluşturuldu

# Altyazı dosyasına yazma
subtitle_file.write(subtitle_content)
subtitle_file.close()

# Oluşturulan altyazıyı videoya yerleştirme (video işleme kütüphanesi kullanılarak)
# Bu kısmı, kullanacağınız video işleme kütüphanesine uyacak şekilde ayarlamanız gerekebilir
# Örneğin, 'moviepy' veya 'OpenCV' gibi kütüphaneler kullanılabilir
