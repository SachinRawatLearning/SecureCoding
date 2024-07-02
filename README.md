Encoding and Encryption

    Encoding :

        - Mapping of information to symbols
            - From ASCII to sheet music
            - Even speech is form of encoding

    Encryption :

        - Process of converting messages in ordinary language, or other information into a secret form that
        cannot be interpreted without knowing the secret method for interpretation called key.

    Serialization :

        - Encoding of an object for storage or transport (Encode to json,xml, etc)
        - Dont ever serialize to binary format.
        - Dont confuse scope (private, public) with security
            - Ex: if suppose we have json object with key as SSN, now this SSN is private, but this object
                is serialized for transport to and API call, the sterilizer has got to pack that internal
                variable into serialization format in plaintext unless we make it otherwise.

Nature of Security on Internet

    - Internet does not operate according to dedicated pathways of communication.
    - Internet is a routed network, which means different routes are possible.

Version Control

    - Secrets do not belong in version control (passwords, certificates, sensitive data, etc.)
    - Version Control is a Context-Enforcer
        - Once you get something in version control, it's very hard to get it truly and completley out
    - Right way to control Secrets
        - Secure build parameters(getting secrets out of build)
        - Encrypt secrets in database
        - Dedicated Secret Store
            - Asset you can connect to and get secrets from API call
            - Example: Azure key valut or AWS Secrets Manager
        - Password free Authentication is preferred
        - Environment variables
    - Separation of duties
        - Lock main branch and accept new code only through pull requests
        - Pull Requests Reviews
        - Different Deployment Resource
