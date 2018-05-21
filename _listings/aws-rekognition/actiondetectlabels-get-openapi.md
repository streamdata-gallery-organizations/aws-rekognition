---
swagger: "2.0"
x-collection-name: AWS Rekognition
x-complete: 0
info:
  title: AWS Rekognition API Detect Labels
  version: 1.0.0
  description: |-
    Detects instances of real-world labels within an image (JPEG or PNG)
           provided as input.
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /?Action=CompareFaces:
    get:
      summary: Compare Faces
      description: |-
        Compares a face in the source input image with
              each face detected in the target input image.
      operationId: compareFaces
      x-api-path-slug: actioncomparefaces-get
      parameters:
      - in: query
        name: SimilarityThreshold
        description: The minimum level of confidence in the match you want included
          in the result
        type: string
      - in: query
        name: SourceImage
        description: Source image either as bytes or an S3 object
        type: string
      - in: query
        name: TargetImage
        description: Target image either as bytes or an S3 object
        type: string
      responses:
        200:
          description: OK
      tags:
      - Faces
  /?Action=CreateCollection:
    get:
      summary: Create Collection
      description: Creates a collection in an AWS Region.
      operationId: createCollection
      x-api-path-slug: actioncreatecollection-get
      parameters:
      - in: query
        name: CollectionId
        description: ID for the collection that you are creating
        type: string
      responses:
        200:
          description: OK
      tags:
      - Collections
  /?Action=DeleteCollection:
    get:
      summary: Delete Collection
      description: Deletes the specified collection.
      operationId: deleteCollection
      x-api-path-slug: actiondeletecollection-get
      parameters:
      - in: query
        name: CollectionId
        description: ID of the collection to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Collections
  /?Action=DeleteFaces:
    get:
      summary: Delete Faces
      description: Deletes faces from a collection.
      operationId: deleteFaces
      x-api-path-slug: actiondeletefaces-get
      parameters:
      - in: query
        name: CollectionId
        description: Collection from which to remove the specific faces
        type: string
      - in: query
        name: FaceIds
        description: An array of face IDs to delete
        type: string
      responses:
        200:
          description: OK
      tags:
      - Faces
  /?Action=DetectFaces:
    get:
      summary: Detect Faces
      description: Detects faces within an image (JPEG or PNG) that is provided as
        input.
      operationId: detectFaces
      x-api-path-slug: actiondetectfaces-get
      parameters:
      - in: query
        name: Attributes
        description: A list of facial attributes you would like to be returned
        type: string
      - in: query
        name: Image
        description: The image in which you want to detect faces
        type: string
      responses:
        200:
          description: OK
      tags:
      - Faces
  /?Action=DetectLabels:
    get:
      summary: Detect Labels
      description: |-
        Detects instances of real-world labels within an image (JPEG or PNG)
               provided as input.
      operationId: detectLabels
      x-api-path-slug: actiondetectlabels-get
      parameters:
      - in: query
        name: Image
        description: The input image
        type: string
      - in: query
        name: MaxLabels
        description: Maximum number of labels you want the service to return in the
          response
        type: string
      - in: query
        name: MinConfidence
        description: Specifies the minimum confidence level for the labels to return
        type: string
      responses:
        200:
          description: OK
      tags:
      - Labels
x-streamrank:
  polling_total_time_average: 0
  polling_size_download_average: 0
  streaming_total_time_average: 0
  streaming_size_download_average: 0
  change_yes: 0
  change_no: 0
  time_percentage: 0
  size_percentage: 0
  change_percentage: 0
  last_run: ""
  days_run: 0
  minute_run: 0
---