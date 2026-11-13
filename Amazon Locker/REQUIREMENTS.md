Amazon Locker is a self service package pickup system. A delivery driver deposits a package into an available compartment, the system generates an access token, and the customer uses that code to retrieve their package.

Requirements-
1. Carrier deposits a package by specifying size (small, medium, large)
    - System assigns an available compartment of matching size
    - Opens compartment and returns access token, or error if no space
2. Upon successfull deposit, an access token is generated and returned 
    - One access token per package
3. User retrieves package by entering access token
    - System validates code and opens compartment 
    - Throws specific error if code is invalid or expired
4. Access tokens expire after 7 days
    - Expired codes are rejected if used for pickup
    - Package remains in compartment until staff removes it
5. Staff can open all expired compartments to manually hande packages 
    - System opens all compartments with expired tokens
    - Staff physically removes packages and returns them to sender
6. Invalid access tokens are rejected with clear error messages
    - Wrong code, already used, or expired - user gets specific feedback

Out of scope:
- How the package gets to the locker
- How the access token reaches the customer 
- Lockout after failed access token attempts 
- UI/rendering layer
- Multiple locker stations 
- Payment or pricing


Core Entities:
- Locker
- Compartment
- AccessToken