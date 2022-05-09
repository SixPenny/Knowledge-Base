#  Interfaces to PCE
[原文地址](https://w.amazon.com/bin/view/CASEOnboarding/Onboarding/PCEOnboarding)

Clients call PCE APIs to read, create, or modify purchase contracts through one of its interfaces. PCE has multiple interfaces each supporting a different client need/requirement. Each interface exposes different API's, so please go through the interfaces below and apply for appropriate permissions.

## PCE Interface

PCEInterface exposes a set of primitive APIs used to access and manipulate purchase contracts. These include APIs for creating, accessing, validating and signing purchase Documents. APIs for setting specific Aspect entities on the purchase Document (setXAndSave, setXAndSign and setXTrial, where X is an Aspect entity) are also supported on this interface.

Brazil Packages:

1.  [https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEInterface](https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEInterface)
2.  [https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEClientConfig](https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEClientConfig)

## PCEBasic Interface

The current supposed caller for this interface is Cart. If your team want to use this interface, make sure to contact cmp@amazon.com first to allow us to understand your use cases.

PCEBasicInterface exposes a set of primitive APIs used to evaluate, validate and set the input document. It does NOT have loadDocument or saveDocument steps. Further, it does NOT have any call to OMA thus it is a pure CASE based interface. It means the APIs may miss some evaluate or validate functions as are supported by hybridly calling OMA.

The APIs in PCEBasicInterface include GetValidatedDocument, which evaluates and validates the input document and returns the evaluated document and a list of constraint violation exceptions if any. It contains setter APIs that set specific Aspect entities on the input Document (setX where X is an Aspect entity), then do evaluate and validate, return the evaluated document and a list of constraint violation exceptions if any.

Brazil Packages:

1.  [https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEBasicInterface](https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEBasicInterface)
2.  [https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEBasicClientConfig](https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEBasicClientConfig)

## PCELegacy Interface

PCELegacy Interface supports a set of APIs that are meant for clients in the process of migrating to the PCEInterface. Clients that still have dependency on the legacy data model (BO structure) may use APIs exposed on the PCELegacy interface to access both Document and BOs. Currently the set of APIs supported on this interface are setPaymentPlan{AndSave|AndSign|Trial}AndReturnLegacyView.

Brazil Packages:

1.  [https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCELegacyInterface](https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCELegacyInterface)
2.  [https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEClientConfig](https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEClientConfig)

## PCEExtended Interface

PCEExtended Interface supports APIs that provide some high level functionality by composing functionality already supported in PCE Interface. For instance, consider a client that wishes to get a purchase and validate it in one go. For it calling PCE.getPurchase() followed by PCE.validatePurchase() might not be very efficient considering that multiple round trips needed to accomplish this. Such clients can call the getValidatedPurchase API supported on the PCEExtended interface to access functionality that is a simple chaining of getPurchase and validatePurchase functions.

Brazil Packages:

1.  [https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEExtendedInterface](https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEExtendedInterface)
2.  [https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEClientConfig](https://devcentral.amazon.com/ac/brazil/directory/package/overview/PCEClientConfig)