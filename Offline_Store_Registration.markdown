# Offline Store Registration Features

This document describes the features and requirements for registering an offline store on an e-commerce application targeting users in South Korea, including both Korean and Vietnamese users.

## Registration Fields

Below is the detailed specification of the fields required for offline store registration:

1. **Personal Name**  
   - **Type**: Input Text  
   - **Required**: Yes  
   - **Constraints**: Maximum 100 characters  
   - **Examples**:  
     - ji chang wook  
     - Nguyễn Văn A  

2. **Store/Company Name**  
   - **Type**: Input Text  
   - **Required**: Yes  
   - **Constraints**: Maximum 100 characters, must be unique (no duplicates with other stores)  
   - **Example**: Hoa Bằng Quận 7  

3. **Store Logo**  
   - **Type**: Imagebox  
   - **Required**: Yes  
   - **Constraints**: Maximum 1 image  
   - **Example**: logo.jpg  

4. **Store Real Photos**  
   - **Type**: Imagebox  
   - **Required**: Yes  
   - **Constraints**: Maximum 10 images  
   - **Example**: img1.jpg, img2.jpg  

5. **Email**  
   - **Type**: Input Email  
   - **Required**: Yes  
   - **Constraints**: Must follow valid email format  
   - **Example**: shop@email.com  

6. **Phone Number**  
   - **Type**: Input Text + OTP Verification  
   - **Required**: Yes  
   - **Constraints**: 9–11 digits, valid South Korean phone number format, requires OTP verification  
   - **Example**: 010-1234-5678  

7. **Store Introduction**  
   - **Type**: Textarea  
   - **Required**: Yes  
   - **Constraints**: Maximum 200 characters  
   - **Example**: Shop hoa tươi, thiết kế theo yêu cầu  

8. **Website**  
   - **Type**: Input Text  
   - **Required**: No  
   - **Constraints**: None  
   - **Example**: (Optional field, can be left blank)  

9. **Operating Hours**  
   - **Type**: Time Range  
   - **Required**: No  
   - **Constraints**: Valid time format (HH:mm–

System: HH:mm), defaults to "All Day" if left blank  
   - **Example**: 08:00 – 21:00  

10. **Business Type**  
    - **Type**: Radio Group  
    - **Required**: Yes  
    - **Constraints**: Select one from the following options:  
      - Brand Owner  
      - Manufacturer  
      - Consignment Sales  
      - Retail with Imported Goods  
      - Direct Importer  
    - **Example**: Brand Owner  

11. **Business Registration Number**  
    - **Type**: Input Text  
    - **Required**: Yes  
    - **Constraints**: Valid business registration number  
    - **Example**: (Unique business registration code)  

12. **Director Name(s)**  
    - **Type**: List<Input Text>  
    - **Required**: Yes  
    - **Constraints**: Valid names, supports multiple directors by adding additional fields  
    - **Example**: (One or more director names)  

13. **Company Address**  
    - **Type**: Multiple Input Fields  
    - **Required**: Yes  
    - **Constraints**: Must follow South Korean address format with Road Name Address system  
    - **Fields**:
      - House Number: Text input (max 10 characters)
      - Street Name: Text input (max 100 characters) with suffixes: -daero (avenue), -ro (road), -gil (lane)
      - District (Gu): Text input (max 50 characters)
      - City (Si): Text input (max 50 characters)  
      - Postal Code: 5-digit number (max 5 characters)
    - **Example**: 12 Sapyeong-daero 58-gil, Seocho-gu, Seoul, 06690, Republic of Korea
    - **Note**: South Korea uses Road Name Address system since 2011, replacing the old land-lot based system. House numbers increase by 2 units every 20 meters along the road, with odd numbers on the left and even numbers on the right.

14. **Business License Image**  
    - **Type**: Imagebox  
    - **Required**: Yes  
    - **Constraints**: Maximum 1 image  
    - **Example**: (Image of business license)  

15. **Agree to Terms and Policies**  
    - **Type**: Checkbox  
    - **Required**: Yes  
    - **Constraints**: Must be checked to proceed  
    - **Example**: ✔  

16. **Back Button**  
    - **Type**: Button  
    - **Required**: No  
    - **Function**: Returns to the previous step for editing  
    - **Example**: —  

17. **Continue Button**  
    - **Type**: Button  
    - **Required**: Yes  
    - **Function**: Saves entered information and proceeds to the next step  
    - **Example**: —  

## Notes
- The application targets both Korean and Vietnamese users in South Korea, so the interface should support bilingual input (Korean and Vietnamese) where applicable.
- The address search system must integrate with a South Korean address verification API to ensure accuracy.
- OTP verification for phone numbers should comply with South Korean telecommunication standards.
- Image uploads (logo, store photos, business license) should support common formats (e.g., JPG, PNG) with appropriate size limits.
- The system must ensure that the store/company name is unique by checking against existing registered stores.
- The interface should validate all required fields before allowing the user to proceed with the "Continue" button.