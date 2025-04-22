## Prerequisites:

- You are the BTP Sub Account Administrator
- You have installed btp CLI Command. Please follow [Download and Start Using the btp CLI Client](https://help.sap.com/docs/btp/sap-btp-neo-environment/download-and-start-using-btp-cli-client?locale=en-US).

## Procedure:

- 1. Get you **Global Account Subdomain** and **Subaccount ID** as the following pictures:
     ![alt text](image.png)
     ![alt text](image-1.png)
- 2. Log in to a global account of SAP BTP.

  ```bash
  btp login --subdomain <Global Account Subdomain> --user <USER EMAIL> --password <PASSWORD>
  ```

  ![alt text](image-2.png)

- 3. Set the target for commands to a subaccount.

  ```bash
  btp target  -sa <Subaccount ID>
  ```

  ![alt text](image-3.png)

- 4. Check and Assign entitlements of **event mesh** to your subaccount

  check your subaccount entitlements from event mesh with the following commands

  ```bash
  btp list accounts/entitlement| grep enterprise-messaging
  ```

  ![alt text](image-4.png)

  If the results **is blank**, please run the following 2 commands to assign **event mesh** etitlements to the subaccount

  ```bash
  btp  assign accounts/entitlement --for-service enterprise-messaging --plan default --amount 1

  btp  assign accounts/entitlement --for-service enterprise-messaging-hub --plan standard --amount 1

  ```

- 5. Check and Assign entitlements of **SAP Work Zone Standard** to your subaccount

  check your subaccount entitlements from event mesh with the following commands

  ```bash
  btp list accounts/entitlement| grep SAPWorkZone
  ```

  ![alt text](image-5.png)

  If the results **is blank**, please run the following command to assign **SAP Work Zone Standard** etitlement to the subaccount

  ```bash
  btp  assign accounts/entitlement --for-service SAPWorkZone --plan standard --amount 1
  ```

- 6. Check and Assign entitlements of **SAP Document Management service, integration option** to your subaccount

  check your subaccount entitlements from event mesh with the following commands

  ```bash
  btp list accounts/entitlement| grep sdm
  ```

  ![alt text](image-6.png)

  If the results **is blank**, please run the following command to assign **SAP Document Management service, integration option** etitlement to the subaccount

  ```bash
  btp  assign accounts/entitlement --for-service sdm --plan standard --amount 1
  ```

- 7. Check and Assign entitlements of **SAP Business Application Studio** to your subaccount

  check your subaccount entitlements from event mesh with the following commands

  ```bash
  btp list accounts/entitlement | grep sapappstudio
  ```

  ![alt text](image-7.png)

  If the results **is blank**, please run the following command to assign **SAP Business Application Studio** etitlement to the subaccount

  ```bash
  btp  assign accounts/entitlement --for-service sapappstudio --plan standard-edition --amount 1
  ```
