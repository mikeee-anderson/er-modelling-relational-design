# Q1 Assumptions — Smart Home IoT System

1. `timestamp` is assumed to be unique per device and serves as the partial key for the weak entity `Sensor Reading`
2. `House Address` is treated as a composite attribute consisting of street, suburb, city and postcode
3. A `User` may exist in the system without having accessed any device (partial participation)
4. A `House` may exist in the system with no devices installed (partial participation)
5. `accessLevel` domain is restricted to: admin, user or guest
6. `operationalStatus` domain is restricted to: active, inactive or faulty
7. A device must be installed in exactly one house and cannot exist independently (total participation in CONTAINS)
8. Each sensor reading must be produced by exactly one device and cannot exist without one (total participation in GENERATES)
9. `Sensor Reading` is modelled as a weak entity as it cannot be uniquely identified without its owning device
10. `manufacturer` and `model number` are kept as two separate simple attributes as specified in the requirements
