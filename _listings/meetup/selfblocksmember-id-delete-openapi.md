---
swagger: "2.0"
x-collection-name: Meetup
x-complete: 0
info:
  title: Meetup Unblock member
  description: Unblocks a previously blocked member from various interactions with
    the authenticated member on the platform
  version: 1.0.0
host: api.meetup.com
basePath: /
schemes:
- http
produces:
- application/json
consumes:
- application/json
paths:
  /self/blocks/:member_id:
    get:
      summary: Block status
      description: Checks the block status for a target member relative to the authenticated
        member
      operationId: abuse
      x-api-path-slug: selfblocksmember-id-get
      responses:
        200:
          description: OK
      tags:
      - Events
      - Abuse
      - Status
    post:
      summary: Block member
      description: Blocks a target member from various interactions with the authenticated
        member on the platform
      operationId: abuse
      x-api-path-slug: selfblocksmember-id-post
      parameters:
      - in: query
        name: comments
        description: An optional string of text describing why you have chosen to
          block this member
        type: string
      - in: query
        name: report
        description: An optional value that represents a type of abuse the target
          member is being blocked for
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Abuse
      - Members
    delete:
      summary: Unblock member
      description: Unblocks a previously blocked member from various interactions
        with the authenticated member on the platform
      operationId: abuse
      x-api-path-slug: selfblocksmember-id-delete
      responses:
        200:
          description: OK
      tags:
      - Events
      - Abuse
      - Members
  /self/abuse_reports:
    post:
      summary: Report Abuse
      description: Submits a new abuse report for a target member. Abuse reports will
        be followed up on by our Community Support team.
      operationId: abuse
      x-api-path-slug: selfabuse-reports-post
      parameters:
      - in: query
        name: comments
        description: An optional string of text that describes why you are submitting
          this report
        type: string
      - in: query
        name: content_tag
        description: An optional identifier for flagged content that identifies both
          the type and id, where possible, of the content reported
        type: string
      - in: query
        name: member_id
        description: A numeric identifier for the member being reported
        type: string
      - in: query
        name: type
        description: A required identifier for type of abuse you are reporting
        type: string
      - in: query
        name: url
        description: An optional URL for the location of the reported content if one
          exists
        type: string
      responses:
        200:
          description: OK
      tags:
      - Events
      - Abuse
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