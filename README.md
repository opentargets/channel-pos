# Station POS
This is _POS Radio Station_, which implements a collection of channels #opentargets/platform-output-support uses to make announcements as events.

# Channels
## Data Images
This channel announces data images produced by POS for Open Targets Platform data backends:

**Channel Folder**: `data-images`

**Data Model**
```json
{
  "type": "otp-data-image",             // Event Type, in this case an 'OTP Data Image' has been created
  "id": "string",                       // Event ID, it uniquely identifies the event
  "producer": "string",                 // Producer of the event, this is the name of the service that produced the event
  "version": "string",                  // Version of the event producer
  "payload_id": "string",               // Uniquely identifies the payload data model ID (TODO)
  "timestamp": "string",                // Timestamp of the event creation in ISO 8601 format
  "payload": {
    "data_image": {
      "id": "string",                   // Data Image ID, it uniquely identifies the data image
      "project": "string",              // GCP project where the data image is stored
      "self_Url": "string",             // GCP resource self URL of the data image
      "name": "string",                 // Data image name
      "description": "string"           // Data image description
  }
}
```

There are two subchannels:
- _platform_: Announces data images for Open Targets Platform data backends
- _ppp_: Announces data images for Open Targets Platform (Partner Preview)

The announcements are made in the form of a JSON file, which is stored in the respective subchannel folder, the name of the file is *channel_content.jsonl*.

# Copyright
Copyright 2014-2024 EMBL - European Bioinformatics Institute, Genentech, GSK, MSD, Pfizer, Sanofi and Wellcome Sanger Institute

This software was developed as part of the Open Targets project. For more information please see: http://www.opentargets.org

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.