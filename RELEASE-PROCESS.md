# QuietShield customer update process

1. Build and test the Android phone/tablet APK.
2. Sign it with the permanent QuietShield release certificate.
3. Test it on a physical Android phone.
4. Create the GitHub Release and upload the signed APK and checksum.
5. Verify the uploaded APK URL.
6. Update `update.json` last.
7. Verify the raw `update.json` URL.

`update.json` is the release switch. Do not publish a higher version code until
the APK has passed phone testing.
