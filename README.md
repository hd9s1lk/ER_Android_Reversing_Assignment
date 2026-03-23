# ER_Android_Reversing_Assignment

1st_Assignment of ER

# Executive Summary

# User Perspective

# Organization Perspective

# Background

## Date

2026/02/27

## File Name (VirusTotal)

com.phone.junk.clean.smart.apk

# Static Analysis

## File Hashes (VirusTotal)

**MD4** - 6848658879f8c35d6c3252bef794daec

**MD5** - eb3b881048f49355a2d3a9493ab50eba

**SHA-1** - 7e40795e3884109ae87348ca700b4c04dc8751c8

**SHA-256** - 4e819b297c4f1a77a29ebf744df05ad9977e704c54fec73a65c219aa78dfb889

**SHA-512** - ca8013005bcb1f47c95a737d48eab7116ae45aa1c0d01e983b8b95d32df24795db6b929e916c8f04ec87fe076ca2ac58a3e75db451ea051b893631f495114c6a

**VHASH** - 4ce2832a29aaa75f13fc01a63c88b160

**SSDEEP** - 393216:rPLgXiODT06HXAi8C8IbE7iV6UhTLsoBB2Bhg7hJkjfs6ByYmZheN1D/R:DLODo6wNJEEOsUhPBYzgtJkjVByYmCnV

**TLSH** - T1F02733A7F328A42FD87330B18EBB421385995D4682436F63E915B21D1DB79C48F5AFC8

## File Size

21398921 bytes (20.41 MB)

## File Type

APK – Android Package Kit

# Signature

**Type:** X.509

**Version:** 3

**Serial number:** 0x754d71c472a3be7037e7b7bf143abe1628e05cdb

**Subject:** CN=Android, OU=Android, O=Google Inc., L=Mountain View, ST=California, C=US
**Valid from:** Wed Feb 25 08:51:21 WET 2026

**Valid until:** Fri Feb 25 08:51:21 WET 2056
**Public key type:** RSA

**Exponent:** 65537
**Modulus size (bits):** 4096

**Modulus:** 659496229831164718229890885341834523651689548564760088000918587208932886309124258807901473906081560808079623563840908412893654170209389235885857221055644284166947955841547810982059934562542839903660556116673453539820656605206735915284051911011522919938400070637969049037155196524419935385364020031607435501481678312493060220468529264498494227421375419785102658826013832398601105165232219884505099761734070270865537363043445947700683958665778925960219108221582841367645382927209718195365826888073035682371547015165905622216600075433822015880253734928176076133484947380602856912236746328044836816683511993150756351514502171483915498803697747692636380516363873489208117553883390921301382276275891730291801025780134484232506995107384049476033388887002384232489803531933411329902947898088391314147502168465140561034506689805592576030550610744015128768232926423191114538151545019374928221968627379840286336103556299815043318098503486788011760251416969288209802033576856439845439612845710912681948660136784638156447516972035349368633023550874110951942365743522019753101672049130034334115978530304896010201726572686714854256937088294259076369498838261388242957506477343544740895015867822044246243161066529065043827909919318139553748510084237

**Signature type:** SHA256withRSA

**Signature OID:** 1.2.840.113549.1.1.11

**MD5 Fingerprint:** 62 1E F6 F8 C9 BB 1D E4 EA 6E 71 7C 09 AD E4 00

**SHA-1 Fingerprint:** 3D 28 47 DB C4 28 2C CA B4 9C D6 F6 27 77 DE 0A 6A 92 72 72

**SHA-256 Fingerprint:** 54 27 C7 A8 11 CE 96 95 08 55 C0 0B 0C 5C 1E 2B 43 37 E1 C7 44 50 65 A8 7B FC E3 75 C8 82 A3 DC

**Packer/Compiler Info** – Java/Kotlin

**Version (VirusTotal)** – Internal Version: 1

**Displayed Version:** 1.0.8.1

**Minimum SDK Version:** 24

**Target SDK Version:** 36

**File Header Characteristics:** 50 4b 03 04 (PK)

**Language (DetectitEasy)** – Kotlin

# External Dependecies:

 **OKHttp3:**

 ![Strings](images/okhttp3_strings.PNG)
 ![okhttp3](images/okhttp3.PNG)

 **Entropy:**
 ![entropy](images/entropy.PNG)

# AndroidManifest.xml

 One of the files that DetectitEasy was able to obtain was the AndroidManifest.xml. This is a file that is critical for the application, defining information like permissions, activities, intents and services. In our application, the following permissions were found:

 ![permissions](images/permissions.PNG)

 **Acceptable Permissions**

- android.permission.INTERNET
- android.permission.ACCESS_NETWORK_STATE
- android.permission.WAKE_LOCK
- android.permission.RECEIVE_BOOT_COMPLETED
- android.permission.REQUEST_DELETE_PACKAGES

 **Outside Communications**

- android.permission.ACCESS_ADSERVICES_AD_ID
- com.google.android.gms.permission.AD_ID
- android.permission.ACCESS_ADSERVICES_TOPICS
- android.permission.ACCESS_ADSERVICES_ATTRIBUTION
- com.google.android.finsky.permission.BIND_GET_INSTALL_REFERRER_SERVICE
- com.google.android.providers.gsf.permission.READ_GSERVICES

 **Controlling the Device**

- android.permission.MANAGE_EXTERNAL_STORAGE
- android.permission.PACKAGE_USAGE_STATS
- android.permission.BIND_JOB_SERVICE
- android.permission.BIND_NOTIFICATION_LISTENER_SERVICE
- android.permission.DUMP
- android.permission.POST_NOTIFICATIONS
- android.permission.READ_EXTERNAL_STORAGE
- android.permission.WRITE_EXTERNAL_STORAGE
  **OSINT**
- android.permission.ACCESS_NETWORK_STATE

The permissions shown here are mostly used on malware. There are a lot of permissions about managing the storage (ex: `MANAGE_EXTERNAL_STORAGE` allows the app to full access to external storage and files on behalf of the user.). Not only that but we also have `POST_NOTIFICATIONS` as this allows the app to post notifications. It’s even considered as dangerous by developer.android.com, `BIND_JOB_SERVICE` which is an Android permission for apps to perform any Background Tasks, `DUMP` allows the app to retrieve the state information from the whole system and `WRITE_EXTERNAL_STORAGE` allows the app to write to external storage. It’s also considered dangerous.
There’s also an extra information being read (OSINT-related), as the `ACCESS_NETWORK_STATE` is also present on the AndroidManifest file, and this gives access about all the networks of our device.


# Behavioral Analysis

**Setup**

In order to perform the dynamic analysis, the main apk file was first sent to the JADX for further investigation.

**Live Memory Dump**

- `ICommonParams`
  - First we noticed the creation of an interface (`ICommonParams`) that saves multiple information about the user into a Map structure, such as `DeviceID` or `UserID`. For each piece of data we did the full code flow.
  
```java
  package com.apm.insight;
  import java.util.List;
  import java.util.Map;

  /* JADX INFO: compiled from: r8-map-id-ce88e2bd4288c86909bdaac64d4c96611d145c55c02c55c7cc9024d475899202 */
  /* JADX INFO: loaded from: classes.dex */
  public interface ICommonParams {
    Map<String, Object> getCommonParams();

    String getDeviceId();

    List<String> getPatchInfo();

    Map<String, Integer> getPluginInfo();

    String getSessionId();

    long getUserId();
  } 
  ```


