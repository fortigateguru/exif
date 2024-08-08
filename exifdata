from PIL import Image
import streamlit as st
from PIL.ExifTags import TAGS


st.image("lens-158471_640.png")
st.title("Image Exif Data")

# Open an image file
uploaded_file = st.file_uploader("Choose an image file", type=["jpg", "jpeg", "png"])
if uploaded_file:
    image = Image.open(uploaded_file)
    st.image(image)

    if st.button("Show Exif Data"):
        # Extract EXIF data
        exif_data = image._getexif()
        # st.write(exif_data)

        # Print EXIF data
        if exif_data:
            exif_info = {}
            for tag, value in exif_data.items():
                tag_name = TAGS.get(tag, tag)
                exif_info[tag_name] = value

            st.write(exif_info)
        else:
            st.write("No EXIF data found.")
