import qrcode

def generate_qr_code(data, file_path):
    qr = qrcode.QRCode(
        version=1,
        error_correction=qrcode.constants.ERROR_CORRECT_L,
        box_size=10,
        border=4,
    )

    qr.add_data(data)
    qr.make(fit=True)

    img = qr.make_image(fill_color="black", back_color="white")
    img.save(file_path)

if __name__ == "__main__":
    data = "https://www.example.com"
    file_path = "example_qr_code.png"

    generate_qr_code(data, file_path)
    print(f"QR code generated and saved to {file_path}")

