..
.. Copyright (c) 2024 ZettaScale Technology
..
.. This program and the accompanying materials are made available under the
.. terms of the Eclipse Public License 2.0 which is available at
.. http://www.eclipse.org/legal/epl-2.0, or the Apache License, Version 2.0
.. which is available at https://www.apache.org/licenses/LICENSE-2.0.
..
.. SPDX-License-Identifier: EPL-2.0 OR Apache-2.0
..
.. Contributors:
..   ZettaScale Zenoh Team, <zenoh@zettascale.tech>
..

*************
API Reference
*************

Containers
=============

Slice
-----
  
Represents an array of bytes.

Types
^^^^^
  
See details at :ref:`owned_types_concept`

.. c:type:: z_owned_slice_t
.. c:type:: z_view_slice_t
.. c:type:: z_loaned_slice_t
.. c:type:: z_moved_slice_t


Functions
^^^^^^^^^

.. autocfunction:: primitives.h::z_slice_empty
.. autocfunction:: primitives.h::z_slice_copy_from_buf
.. autocfunction:: primitives.h::z_slice_from_buf
.. autocfunction:: primitives.h::z_slice_data
.. autocfunction:: primitives.h::z_slice_len
.. autocfunction:: primitives.h::z_slice_is_empty

.. autocfunction:: primitives.h::z_view_slice_from_buf
.. c:function:: void z_view_slice_empty(z_view_slice_t * slice)

  See :c:func:`z_slice_empty`


Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_slice_drop(z_moved_slice_t * slice) 
.. c:function:: void z_slice_clone(z_owned_slice_t * dst, const z_loaned_slice_t * slice) 
.. c:function:: const z_loaned_slice_t * z_view_slice_loan(const z_view_slice_t * slice)
.. c:function:: z_loaned_slice_t * z_view_slice_loan_mut(z_view_slice_t * slice)
.. c:function:: const z_loaned_slice_t * z_slice_loan(const z_owned_slice_t * slice)
.. c:function:: z_loaned_slice_t * z_slice_loan_mut(z_owned_slice_t * slice)


String
------
  
Represents a string without null-terminator.

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_string_t
.. c:type:: z_view_string_t
.. c:type:: z_loaned_string_t
.. c:type:: z_moved_string_t

Functions
^^^^^^^^^

.. autocfunction:: primitives.h::z_string_empty
.. autocfunction:: primitives.h::z_string_copy_from_str
.. autocfunction:: primitives.h::z_string_copy_from_substr
.. autocfunction:: primitives.h::z_string_from_str
.. autocfunction:: primitives.h::z_string_data
.. autocfunction:: primitives.h::z_string_len
.. autocfunction:: primitives.h::z_string_is_empty
.. autocfunction:: primitives.h::z_string_as_slice

.. autocfunction:: primitives.h::z_view_string_from_str
.. autocfunction:: primitives.h::z_view_string_from_substr
.. c:function:: void z_view_string_empty(z_view_string_t * string)

  See :c:func:`z_string_empty`

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_string_drop(z_moved_string_t * string) 
.. c:function:: void z_string_clone(z_owned_string_t * dst, const z_loaned_string_t * string) 
.. c:function:: const z_loaned_string_t * z_view_string_loan(const z_view_string_t * string)
.. c:function:: z_loaned_string_t * z_view_string_loan_mut(z_view_string_t * string)
.. c:function:: const z_loaned_string_t * z_string_loan(const z_owned_string_t * string)
.. c:function:: z_loaned_string_t * z_string_loan_mut(z_owned_string_t * string)


String Array
------------

Represents an array of non null-terminated strings.

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_string_array_t
.. c:type:: z_loaned_string_array_t
.. c:type:: z_moved_string_array_t

Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_string_array_new
.. autocfunction:: primitives.h::z_string_array_push_by_alias
.. autocfunction:: primitives.h::z_string_array_push_by_copy
.. autocfunction:: primitives.h::z_string_array_get
.. autocfunction:: primitives.h::z_string_array_len
.. autocfunction:: primitives.h::z_string_array_is_empty

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_string_array_drop(z_moved_string_array_t * string_array) 
.. c:function:: void z_string_array_clone(z_owned_string_array_t * dst, const z_loaned_string_array_t * string_array) 
.. c:function:: const z_loaned_string_array_t * z_string_array_loan(const z_owned_string_array_t * string_array)
.. c:function:: z_loaned_string_array_t * z_string_array_loan_mut(z_owned_string_array_t * string_array)


Common
======

Key expression
--------------

Represents a key expression in Zenoh.

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_keyexpr_t
.. c:type:: z_view_keyexpr_t
.. c:type:: z_loaned_keyexpr_t
.. c:type:: z_moved_keyexpr_t

.. autocenum:: constants.h::z_keyexpr_intersection_level_t
.. autocenum:: constants.h::zp_keyexpr_canon_status_t

Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_keyexpr_from_str
.. autocfunction:: primitives.h::z_view_keyexpr_from_str
.. autocfunction:: primitives.h::z_keyexpr_from_str_autocanonize
.. autocfunction:: primitives.h::z_view_keyexpr_from_str_autocanonize
.. autocfunction:: primitives.h::z_view_keyexpr_from_str_unchecked
.. autocfunction:: primitives.h::z_keyexpr_from_substr
.. autocfunction:: primitives.h::z_view_keyexpr_from_substr
.. autocfunction:: primitives.h::z_keyexpr_from_substr_autocanonize
.. autocfunction:: primitives.h::z_view_keyexpr_from_substr_autocanonize
.. autocfunction:: primitives.h::z_view_keyexpr_from_substr_unchecked

.. autocfunction:: primitives.h::z_keyexpr_as_view_string

.. autocfunction:: primitives.h::z_keyexpr_canonize
.. autocfunction:: primitives.h::z_keyexpr_canonize_null_terminated
.. autocfunction:: primitives.h::z_keyexpr_is_canon

.. autocfunction:: primitives.h::z_keyexpr_concat
.. autocfunction:: primitives.h::z_keyexpr_join
.. autocfunction:: primitives.h::z_keyexpr_equals
.. autocfunction:: primitives.h::z_keyexpr_includes
.. autocfunction:: primitives.h::z_keyexpr_intersects
.. autocfunction:: primitives.h::z_keyexpr_relation_to

.. autocfunction:: primitives.h::z_declare_keyexpr
.. autocfunction:: primitives.h::z_undeclare_keyexpr

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_keyexpr_drop(z_moved_keyexpr_t * keyexpr) 
.. c:function:: void z_keyexpr_clone(z_owned_keyexpr_t * dst, const z_loaned_keyexpr_t * keyexpr) 
.. c:function:: const z_loaned_keyexpr_t * z_view_keyexpr_loan(const z_view_keyexpr_t * keyexpr)
.. c:function:: z_loaned_keyexpr_t * z_view_keyexpr_loan_mut(z_view_keyexpr_t * keyexpr)
.. c:function:: const z_loaned_keyexpr_t * z_keyexpr_loan(const z_owned_keyexpr_t * keyexpr)
.. c:function:: z_loaned_keyexpr_t * z_keyexpr_loan_mut(z_owned_keyexpr_t * keyexpr)


Encoding
--------
  
Represents the encoding of a payload, in a MIME-like format.

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_encoding_t
.. c:type:: z_loaned_encoding_t
.. c:type:: z_moved_encoding_t

Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_encoding_from_str
.. autocfunction:: primitives.h::z_encoding_from_substr
.. autocfunction:: primitives.h::z_encoding_set_schema_from_str
.. autocfunction:: primitives.h::z_encoding_set_schema_from_substr
.. autocfunction:: primitives.h::z_encoding_to_string
.. autocfunction:: primitives.h::z_encoding_equals
.. autocfunction:: encoding.h::z_encoding_loan_default

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_encoding_drop(z_moved_encoding_t * encoding) 
.. c:function:: void z_encoding_clone(z_owned_encoding_t * dst, const z_loaned_encoding_t * encoding) 
.. c:function:: const z_loaned_encoding_t * z_encoding_loan(const z_owned_encoding_t * encoding)
.. c:function:: z_loaned_encoding_t * z_encoding_loan_mut(z_owned_encoding_t * encoding)


Predefined Encodings
^^^^^^^^^^^^^^^^^^^^
.. autocfunction:: encoding.h::z_encoding_zenoh_bytes
.. autocfunction:: encoding.h::z_encoding_zenoh_int8
.. autocfunction:: encoding.h::z_encoding_zenoh_int16
.. autocfunction:: encoding.h::z_encoding_zenoh_int32
.. autocfunction:: encoding.h::z_encoding_zenoh_int64
.. autocfunction:: encoding.h::z_encoding_zenoh_int128
.. autocfunction:: encoding.h::z_encoding_zenoh_uint8
.. autocfunction:: encoding.h::z_encoding_zenoh_uint16
.. autocfunction:: encoding.h::z_encoding_zenoh_uint32
.. autocfunction:: encoding.h::z_encoding_zenoh_uint64
.. autocfunction:: encoding.h::z_encoding_zenoh_uint128
.. autocfunction:: encoding.h::z_encoding_zenoh_float32
.. autocfunction:: encoding.h::z_encoding_zenoh_float64
.. autocfunction:: encoding.h::z_encoding_zenoh_bool
.. autocfunction:: encoding.h::z_encoding_zenoh_string
.. autocfunction:: encoding.h::z_encoding_zenoh_error
.. autocfunction:: encoding.h::z_encoding_application_octet_stream
.. autocfunction:: encoding.h::z_encoding_text_plain
.. autocfunction:: encoding.h::z_encoding_application_json
.. autocfunction:: encoding.h::z_encoding_text_json
.. autocfunction:: encoding.h::z_encoding_application_cdr
.. autocfunction:: encoding.h::z_encoding_application_cbor
.. autocfunction:: encoding.h::z_encoding_application_yaml
.. autocfunction:: encoding.h::z_encoding_text_yaml
.. autocfunction:: encoding.h::z_encoding_text_json5
.. autocfunction:: encoding.h::z_encoding_application_python_serialized_object
.. autocfunction:: encoding.h::z_encoding_application_protobuf
.. autocfunction:: encoding.h::z_encoding_application_java_serialized_object
.. autocfunction:: encoding.h::z_encoding_application_openmetrics_text
.. autocfunction:: encoding.h::z_encoding_image_png
.. autocfunction:: encoding.h::z_encoding_image_jpeg
.. autocfunction:: encoding.h::z_encoding_image_gif
.. autocfunction:: encoding.h::z_encoding_image_bmp
.. autocfunction:: encoding.h::z_encoding_image_webp
.. autocfunction:: encoding.h::z_encoding_application_xml
.. autocfunction:: encoding.h::z_encoding_application_x_www_form_urlencoded
.. autocfunction:: encoding.h::z_encoding_text_html
.. autocfunction:: encoding.h::z_encoding_text_xml
.. autocfunction:: encoding.h::z_encoding_text_css
.. autocfunction:: encoding.h::z_encoding_text_javascript
.. autocfunction:: encoding.h::z_encoding_text_markdown
.. autocfunction:: encoding.h::z_encoding_text_csv
.. autocfunction:: encoding.h::z_encoding_application_sql
.. autocfunction:: encoding.h::z_encoding_application_coap_payload
.. autocfunction:: encoding.h::z_encoding_application_json_patch_json
.. autocfunction:: encoding.h::z_encoding_application_json_seq
.. autocfunction:: encoding.h::z_encoding_application_jsonpath
.. autocfunction:: encoding.h::z_encoding_application_jwt
.. autocfunction:: encoding.h::z_encoding_application_mp4
.. autocfunction:: encoding.h::z_encoding_application_soap_xml
.. autocfunction:: encoding.h::z_encoding_application_yang
.. autocfunction:: encoding.h::z_encoding_audio_aac
.. autocfunction:: encoding.h::z_encoding_audio_flac
.. autocfunction:: encoding.h::z_encoding_audio_mp4
.. autocfunction:: encoding.h::z_encoding_audio_ogg
.. autocfunction:: encoding.h::z_encoding_audio_vorbis
.. autocfunction:: encoding.h::z_encoding_video_h261
.. autocfunction:: encoding.h::z_encoding_video_h263
.. autocfunction:: encoding.h::z_encoding_video_h264
.. autocfunction:: encoding.h::z_encoding_video_h265
.. autocfunction:: encoding.h::z_encoding_video_h266
.. autocfunction:: encoding.h::z_encoding_video_mp4
.. autocfunction:: encoding.h::z_encoding_video_ogg
.. autocfunction:: encoding.h::z_encoding_video_raw
.. autocfunction:: encoding.h::z_encoding_video_vp8
.. autocfunction:: encoding.h::z_encoding_video_vp9

Reply Error
-----------

Represents a Zenoh reply error value.

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_reply_err_t
.. c:type:: z_loaned_reply_err_t
.. c:type:: z_moved_reply_err_t

Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_reply_err_payload
.. autocfunction:: primitives.h::z_reply_err_encoding

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_reply_err_drop(z_moved_reply_err_t * reply_err) 
.. c:function:: void z_reply_err_clone(z_owned_reply_err_t * dst, const z_loaned_reply_err_t * reply_err) 
.. c:function:: const z_loaned_reply_err_t * z_reply_err_loan(const z_owned_reply_err_t * reply_err)


Sample
------

Represents a data sample.

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_sample_t
.. c:type:: z_loaned_sample_t
.. c:type:: z_moved_sample_t

.. autocenum:: constants.h::z_sample_kind_t

Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_sample_timestamp
.. autocfunction:: primitives.h::z_sample_attachment
.. autocfunction:: primitives.h::z_sample_encoding
.. autocfunction:: primitives.h::z_sample_payload
.. autocfunction:: primitives.h::z_sample_keyexpr
.. autocfunction:: primitives.h::z_sample_priority
.. autocfunction:: primitives.h::z_sample_congestion_control
.. autocfunction:: primitives.h::z_sample_express
.. autocfunction:: primitives.h::z_sample_reliability
.. autocfunction:: primitives.h::z_sample_kind

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_sample_drop(z_moved_sample_t * sample) 
.. c:function:: void z_sample_clone(z_owned_sample_t * dst, const z_loaned_sample_t * sample) 
.. c:function:: const z_loaned_sample_t * z_sample_loan(const z_owned_sample_t * sample)


Timestamp
---------
Types
^^^^^
.. c:type:: z_timestamp_t

Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_timestamp_id
.. autocfunction:: primitives.h::z_timestamp_ntp64_time
.. autocfunction:: primitives.h::z_timestamp_check

Closures
========

A closure is a structure that contains all the elements for stateful, memory-leak-free callbacks:
  - context: a pointer to an arbitrary state.
  - call: the typical callback function. ``context`` will be passed as its last argument.
  - drop: allows the callback's state to be freed. ``context`` will be passed as its last argument.

Closures are not guaranteed not to be called concurrently.

It is guaranteed that:
  - ``call`` will never be called once ``drop`` has started.
  - ``drop`` will only be called **once**, and **after every** ``call`` has ended.
  - The two previous guarantees imply that ``call`` and ``drop`` are never called concurrently.

Sample closure
---------------
Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_closure_sample_t
.. c:type:: z_loaned_closure_sample_t
.. c:type:: z_moved_closure_sample_t
   
Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_closure_sample
.. autocfunction:: primitives.h::z_closure_sample_call

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: const z_loaned_closure_sample_t * z_closure_sample_loan(const z_owned_closure_sample_t * closure)
.. c:function:: void z_closure_sample_drop(z_moved_closure_sample_t * closure) 

Query closure
-------------
Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_closure_query_t
.. c:type:: z_loaned_closure_query_t
.. c:type:: z_moved_closure_query_t
   
Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_closure_query
.. autocfunction:: primitives.h::z_closure_query_call

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: const z_loaned_closure_query_t * z_closure_query_loan(const z_owned_closure_query_t * closure)
.. c:function:: void z_closure_query_drop(z_moved_closure_query_t * closure) 


Reply closure
-------------
Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_closure_reply_t
.. c:type:: z_loaned_closure_reply_t
.. c:type:: z_moved_closure_reply_t
   
Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_closure_reply
.. autocfunction:: primitives.h::z_closure_reply_call

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: const z_loaned_closure_reply_t * z_closure_reply_loan(const z_owned_closure_reply_t * closure)
.. c:function:: void z_closure_reply_drop(z_moved_closure_reply_t * closure) 


Hello closure
-------------
Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_closure_hello_t
.. c:type:: z_loaned_closure_hello_t
.. c:type:: z_moved_closure_hello_t
   
Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_closure_hello
.. autocfunction:: primitives.h::z_closure_hello_call

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: const z_loaned_closure_hello_t * z_closure_hello_loan(const z_owned_closure_hello_t * closure)
.. c:function:: void z_closure_hello_drop(z_moved_closure_hello_t * closure) 


ID closure
----------
Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_closure_zid_t
.. c:type:: z_loaned_closure_zid_t
.. c:type:: z_moved_closure_zid_t
   
Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_closure_zid
.. autocfunction:: primitives.h::z_closure_zid_call

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: const z_loaned_closure_zid_t * z_closure_zid_loan(const z_owned_closure_zid_t * closure)
.. c:function:: void z_closure_zid_drop(z_moved_closure_zid_t * closure) 


.. _channels_concept:

Channels
========

The concept of channels and handlers revolves around managing communication between different components using two types of channels: FIFO (First-In-First-Out) and Ring Buffers. These channels support handling various item types such as sample, reply, and query, with distinct methods available for each.

The FIFO channel ensures that data is received in the order it was sent. It supports blocking and non-blocking (try) reception of data.
If the channel is dropped, the handlers transition into a "gravestone" state, signifying that no more data will be sent or received.

The Ring channel differs from FIFO in that data is overwritten if the buffer is full, but it still supports blocking and non-blocking reception of data. As with the FIFO channel, the handler can be dropped, resetting it to a gravestone state.

The methods common for all channles:

- `z_yyy_channel_xxx_new`: Constructs the send and receive ends of the `yyy` (`fifo` or `ring`) channel for items type `xxx`.
- `z_yyy_handler_xxx_recv`: Receives an item from the channel (blocking). If no more items are available or the channel is dropped, the item transitions to the gravestone state.
- `z_yyy_handler_xxx_try_recv`: Attempts to receive an item immediately (non-blocking). Returns a gravestone state if no data is available.
- `z_yyy_handler_xxx_loan`: Borrows the handler for access.
- `z_yyy_handler_xxx_drop`: Drops the the handler, setting it to a gravestone state.


Sample channel
--------------

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_fifo_handler_sample_t
.. c:type:: z_loaned_fifo_handler_sample_t
.. c:type:: z_owned_ring_handler_sample_t
.. c:type:: z_loaned_ring_handler_sample_t

Methods
^^^^^^^
.. c:function:: void z_fifo_channel_sample_new(z_owned_closure_sample_t * callback, z_owned_fifo_handler_sample_t * handler, size_t capacity)
.. c:function:: void z_ring_channel_sample_new(z_owned_closure_sample_t * callback, z_owned_ring_handler_sample_t * handler, size_t capacity)

See details at :ref:`channels_concept`

.. c:function:: z_result_t z_fifo_handler_sample_recv(const z_loaned_fifo_handler_sample_t * handler, z_owned_sample_t * sample) 
.. c:function:: z_result_t z_fifo_handler_sample_try_recv(const z_loaned_fifo_handler_sample_t * handler, z_owned_sample_t * sample) 
.. c:function:: z_result_t z_ring_handler_sample_recv(const z_loaned_ring_handler_sample_t * handler, z_owned_sample_t * sample) 
.. c:function:: z_result_t z_ring_handler_sample_try_recv(const z_loaned_ring_handler_sample_t * handler, z_owned_sample_t * sample) 

See details at :ref:`channels_concept`

.. c:function:: const z_loaned_fifo_handler_sample_t * z_fifo_handler_sample_loan(const z_owned_fifo_handler_sample_t * handler) 
.. c:function:: void z_fifo_handler_sample_drop(z_moved_fifo_handler_sample_t * handler) 
.. c:function:: const z_loaned_ring_handler_sample_t * z_ring_handler_sample_loan(const z_owned_ring_handler_sample_t * handler) 
.. c:function:: void z_ring_handler_sample_drop(z_moved_ring_handler_sample_t * handler) 

See details at :ref:`owned_types_concept`


Query channel
-------------

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_fifo_handler_query_t
.. c:type:: z_loaned_fifo_handler_query_t
.. c:type:: z_owned_ring_handler_query_t
.. c:type:: z_loaned_ring_handler_query_t

Methods
^^^^^^^
.. c:function:: void z_fifo_channel_query_new(z_owned_closure_query_t * callback, z_owned_fifo_handler_query_t * handler, size_t capacity)
.. c:function:: void z_ring_channel_query_new(z_owned_closure_query_t * callback, z_owned_ring_handler_query_t * handler, size_t capacity)

See details at :ref:`channels_concept`

.. c:function:: z_result_t z_fifo_handler_query_recv(const z_loaned_fifo_handler_query_t * handler, z_owned_query_t * query) 
.. c:function:: z_result_t z_fifo_handler_query_try_recv(const z_loaned_fifo_handler_query_t * handler, z_owned_query_t * query) 
.. c:function:: z_result_t z_ring_handler_query_recv(const z_loaned_ring_handler_query_t * handler, z_owned_query_t * query) 
.. c:function:: z_result_t z_ring_handler_query_try_recv(const z_loaned_ring_handler_query_t * handler, z_owned_query_t * query) 

See details at :ref:`channels_concept`

.. c:function:: const z_loaned_fifo_handler_query_t * z_fifo_handler_query_loan(const z_owned_fifo_handler_query_t * handler) 
.. c:function:: void z_fifo_handler_query_drop(z_moved_fifo_handler_query_t * handler) 
.. c:function:: const z_loaned_ring_handler_query_t * z_ring_handler_query_loan(const z_owned_ring_handler_query_t * handler) 
.. c:function:: void z_ring_handler_query_drop(z_moved_ring_handler_query_t * handler) 

See details at :ref:`owned_types_concept`

Reply channel
-------------

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_fifo_handler_reply_t
.. c:type:: z_loaned_fifo_handler_reply_t
.. c:type:: z_owned_ring_handler_reply_t
.. c:type:: z_loaned_ring_handler_reply_t

Methods
^^^^^^^
.. c:function:: void z_fifo_channel_reply_new(z_owned_closure_reply_t * callback, z_owned_fifo_handler_reply_t * handler, size_t capacity)
.. c:function:: void z_ring_channel_reply_new(z_owned_closure_reply_t * callback, z_owned_ring_handler_reply_t * handler, size_t capacity)

See details at :ref:`channels_concept`

.. c:function:: z_result_t z_fifo_handler_reply_recv(const z_loaned_fifo_handler_reply_t * handler, z_owned_reply_t * reply) 
.. c:function:: z_result_t z_fifo_handler_reply_try_recv(const z_loaned_fifo_handler_reply_t * handler, z_owned_reply_t * reply) 
.. c:function:: z_result_t z_ring_handler_reply_recv(const z_loaned_ring_handler_reply_t * handler, z_owned_reply_t * reply) 
.. c:function:: z_result_t z_ring_handler_reply_try_recv(const z_loaned_ring_handler_reply_t * handler, z_owned_reply_t * reply) 

See details at :ref:`channels_concept`

.. c:function:: const z_loaned_fifo_handler_reply_t * z_fifo_handler_reply_loan(const z_owned_fifo_handler_reply_t * handler) 
.. c:function:: void z_fifo_handler_reply_drop(z_moved_fifo_handler_reply_t * handler) 
.. c:function:: const z_loaned_ring_handler_reply_t * z_ring_handler_reply_loan(const z_owned_ring_handler_reply_t * handler) 
.. c:function:: void z_ring_handler_reply_drop(z_moved_ring_handler_reply_t * handler) 

See details at :ref:`owned_types_concept`


System
======
Random
------
Functions
^^^^^^^^^
.. autocfunction:: platform_common.h::z_random_u8
.. autocfunction:: platform_common.h::z_random_u16
.. autocfunction:: platform_common.h::z_random_u32
.. autocfunction:: platform_common.h::z_random_u64
.. autocfunction:: platform_common.h::z_random_fill

Sleep
------
Functions
^^^^^^^^^
.. autocfunction:: platform_common.h::z_sleep_s
.. autocfunction:: platform_common.h::z_sleep_ms
.. autocfunction:: platform_common.h::z_sleep_us

Time
----

Types
^^^^^
.. c:type:: z_clock_t
.. c:type:: z_time_t

Functions
^^^^^^^^^
.. autocfunction:: platform_common.h::z_clock_now
.. autocfunction:: platform_common.h::z_clock_elapsed_s
.. autocfunction:: platform_common.h::z_clock_elapsed_ms
.. autocfunction:: platform_common.h::z_clock_elapsed_us

.. autocfunction:: platform_common.h::z_time_now
.. autocfunction:: platform_common.h::z_time_elapsed_s
.. autocfunction:: platform_common.h::z_time_elapsed_ms
.. autocfunction:: platform_common.h::z_time_elapsed_us
.. autocfunction:: platform_common.h::z_time_now_as_str


Mutex
-----
Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_mutex_t
.. c:type:: z_loaned_mutex_t
.. c:type:: z_moved_mutex_t

Functions
^^^^^^^^^

.. autocfunction:: platform_common.h::z_mutex_init
.. autocfunction:: platform_common.h::z_mutex_lock
.. autocfunction:: platform_common.h::z_mutex_unlock
.. autocfunction:: platform_common.h::z_mutex_try_lock

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_mutex_drop(z_moved_mutex_t * mutex) 
.. c:function:: const z_loaned_mutex_t * z_mutex_loan(const z_owned_mutex_t * mutex)


Conditional Variable
--------------------
Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_condvar_t
.. c:type:: z_loaned_condvar_t
.. c:type:: z_moved_condvar_t

Functions
^^^^^^^^^
.. autocfunction:: platform_common.h::z_condvar_init
.. autocfunction:: platform_common.h::z_condvar_wait
.. autocfunction:: platform_common.h::z_condvar_signal

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_condvar_drop(z_moved_condvar_t * condvar) 
.. c:function:: const z_loaned_condvar_t * z_condvar_loan(const z_owned_condvar_t * condvar)


Task
----
Types
^^^^^
.. c:type:: z_owned_task_t
.. c:type:: z_moved_task_t

Functions
^^^^^^^^^
.. autocfunction:: platform_common.h::z_task_init
.. autocfunction:: platform_common.h::z_task_join
.. autocfunction:: platform_common.h::z_task_detach
.. autocfunction:: platform_common.h::z_task_drop

Session
=======

Session configuration
---------------------

Represents a Zenoh configuration, used to configure Zenoh sessions upon opening.

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_config_t
.. c:type:: z_loaned_config_t
.. c:type:: z_moved_config_t

Functions
^^^^^^^^^

.. autocfunction:: primitives.h::z_config_new
.. autocfunction:: primitives.h::z_config_default
.. autocfunction:: primitives.h::zp_config_get
.. autocfunction:: primitives.h::zp_config_insert

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: void z_config_drop(z_moved_config_t * config) 
.. c:function:: void z_config_clone(z_owned_config_t * dst, const z_loaned_config_t * config) 
.. c:function:: const z_loaned_config_t * z_config_loan(const z_owned_config_t * config)
.. c:function:: z_loaned_config_t * z_config_loan_mut(z_owned_config_t * config)


Session management
------------------

Represents a Zenoh Session.

Types
^^^^^

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_session_t
.. c:type:: z_loaned_session_t
.. c:type:: z_moved_session_t

.. c:type:: z_id_t

Functions
^^^^^^^^^
.. autocfunction:: primitives.h::z_open
.. autocfunction:: primitives.h::z_close
.. autocfunction:: primitives.h::z_session_is_closed

.. autocfunction:: primitives.h::z_info_zid
.. autocfunction:: primitives.h::z_info_routers_zid
.. autocfunction:: primitives.h::z_info_peers_zid
.. autocfunction:: primitives.h::z_id_to_string

Ownership Functions
^^^^^^^^^^^^^^^^^^^

See details at :ref:`owned_types_concept`

.. c:function:: const z_loaned_session_t * z_session_loan(const z_owned_session_t * closure)
.. c:function:: void z_session_drop(z_moved_session_t * closure) 


Publication
===========

Represents a Zenoh Publisher entity.

Types
-----

See details at :ref:`owned_types_concept`

.. c:type:: z_owned_publisher_t
.. c:type:: z_loaned_publisher_t
.. c:type:: z_moved_publisher_t

Option Types
------------

.. autoctype:: types.h::z_put_options_t
.. autoctype:: types.h::z_delete_options_t
.. autoctype:: types.h::z_publisher_options_t
.. autoctype:: types.h::z_publisher_put_options_t
.. autoctype:: types.h::z_publisher_delete_options_t

Constants
---------

.. autocenum:: constants.h::z_congestion_control_t
.. autocenum:: constants.h::z_priority_t
.. autocenum:: constants.h::z_reliability_t

Functions
---------
.. autocfunction:: primitives.h::z_put
.. autocfunction:: primitives.h::z_delete

.. autocfunction:: primitives.h::z_declare_publisher
.. autocfunction:: primitives.h::z_publisher_put
.. autocfunction:: primitives.h::z_publisher_delete
.. autocfunction:: primitives.h::z_undeclare_publisher
.. autocfunction:: primitives.h::z_publisher_keyexpr

.. autocfunction:: primitives.h::z_put_options_default
.. autocfunction:: primitives.h::z_delete_options_default
.. autocfunction:: primitives.h::z_publisher_options_default
.. autocfunction:: primitives.h::z_publisher_put_options_default
.. autocfunction:: primitives.h::z_publisher_delete_options_default
.. autocfunction:: primitives.h::z_reliability_default

Ownership Functions
-------------------

See details at :ref:`owned_types_concept`

.. c:function:: const z_loaned_publisher_t * z_publisher_loan(const z_owned_publisher_t * closure)
.. c:function:: void z_publisher_drop(z_moved_publisher_t * closure) 


Subscription
============

Types
-----

Represents a Zenoh Subscriber entity.
See details at :ref:`owned_types_concept`

.. c:type:: z_owned_subscriber_t
.. c:type:: z_loaned_subscriber_t
.. c:type:: z_moved_subscriber_t

Option Types
------------

.. autoctype:: types.h::z_subscriber_options_t

Functions
---------

.. autocfunction:: primitives.h::z_declare_subscriber
.. autocfunction:: primitives.h::z_undeclare_subscriber

.. autocfunction:: primitives.h::z_subscriber_options_default
.. autocfunction:: primitives.h::z_subscriber_keyexpr

Ownership Functions
-------------------

See details at :ref:`owned_types_concept`

.. c:function:: const z_loaned_subscriber_t * z_subscriber_loan(const z_owned_subscriber_t * closure)
.. c:function:: void z_subscriber_drop(z_moved_subscriber_t * closure) 


Queryable
=========

Types
-----

Represents a Zenoh Queryable entity.
See details at :ref:`owned_types_concept`

.. c:type:: z_owned_queryable_t
.. c:type:: z_loaned_queryable_t
.. c:type:: z_moved_queryable_t

Represents a Zenoh Query entity, received by Zenoh queryable entities.
See details at :ref:`owned_types_concept`

.. c:type:: z_owned_query_t
.. c:type:: z_loaned_query_t
.. c:type:: z_moved_query_t

Option Types
------------

.. autoctype:: types.h::z_queryable_options_t
.. autoctype:: types.h::z_query_reply_options_t
.. autoctype:: types.h::z_query_reply_err_options_t
.. autoctype:: types.h::z_query_reply_del_options_t

Functions
---------
.. autocfunction:: primitives.h::z_declare_queryable
.. autocfunction:: primitives.h::z_undeclare_queryable

.. autocfunction:: primitives.h::z_queryable_options_default
.. autocfunction:: primitives.h::z_query_reply_options_default
.. autocfunction:: primitives.h::z_query_reply_err_options_default
.. autocfunction:: primitives.h::z_query_reply_del_options_default

.. autocfunction:: primitives.h::z_query_keyexpr
.. autocfunction:: primitives.h::z_query_parameters
.. autocfunction:: primitives.h::z_query_payload
.. autocfunction:: primitives.h::z_query_encoding
.. autocfunction:: primitives.h::z_query_attachment
.. autocfunction:: primitives.h::z_query_reply
.. autocfunction:: primitives.h::z_query_reply_err
.. autocfunction:: primitives.h::z_query_reply_del

Ownership Functions
-------------------

See details at :ref:`owned_types_concept`

.. c:function:: void z_queryable_drop(z_moved_queryable_t * closure) 
.. c:function:: const z_loaned_queryable_t * z_queryable_loan(const z_owned_queryable_t * closure)

.. c:function:: void z_query_drop(z_moved_query_t * query) 
.. c:function:: void z_query_clone(z_owned_query_t * dst, const z_loaned_query_t * query) 
.. c:function:: const z_loaned_query_t * z_query_loan(const z_owned_query_t * query)

Query
=====
Types
-----

Represents the reply to a query.
See details at :ref:`owned_types_concept`

.. c:type:: z_owned_reply_t
.. c:type:: z_loaned_reply_t
.. c:type:: z_moved_reply_t
  
Option Types
------------

.. autoctype:: types.h::z_get_options_t
.. autocenum:: constants.h::z_query_target_t
.. autocenum:: constants.h::z_consolidation_mode_t
.. autoctype:: types.h::z_query_consolidation_t

Functions
---------

.. autocfunction:: primitives.h::z_get
.. autocfunction:: primitives.h::z_get_options_default

.. autocfunction:: primitives.h::z_query_consolidation_default
.. autocfunction:: primitives.h::z_query_consolidation_auto
.. autocfunction:: primitives.h::z_query_consolidation_none
.. autocfunction:: primitives.h::z_query_consolidation_monotonic
.. autocfunction:: primitives.h::z_query_consolidation_latest
.. autocfunction:: primitives.h::z_query_target_default

.. autocfunction:: primitives.h::z_reply_is_ok
.. autocfunction:: primitives.h::z_reply_ok
.. autocfunction:: primitives.h::z_reply_err

Ownership Functions
-------------------

See details at :ref:`owned_types_concept`

.. c:function:: void z_reply_drop(z_moved_reply_t * reply) 
.. c:function:: void z_reply_clone(z_owned_reply_t * dst, const z_loaned_reply_t * reply) 
.. c:function:: const z_loaned_reply_t * z_reply_loan(const z_owned_reply_t * reply)


Scouting
========

Types
-----

Represents the content of a `hello` message returned by a zenoh entity as a reply to a `scout` message.
See details at :ref:`owned_types_concept`

.. c:type:: z_owned_hello_t
.. c:type:: z_loaned_hello_t
.. c:type:: z_moved_hello_t
  
Option Types
------------

.. autoctype:: types.h::z_scout_options_t

Functions
---------
.. autocfunction:: primitives.h::z_scout
.. autocfunction:: primitives.h::z_hello_whatami
.. autocfunction:: primitives.h::z_hello_locators
.. autocfunction:: primitives.h::zp_hello_locators
.. autocfunction:: primitives.h::z_hello_zid
.. autocfunction:: primitives.h::z_whatami_to_view_string
.. autocfunction:: primitives.h::z_scout_options_default

Ownership Functions
-------------------

See details at :ref:`owned_types_concept`

.. c:function:: void z_hello_drop(z_moved_hello_t * hello) 
.. c:function:: void z_hello_clone(z_owned_hello_t * dst, const z_loaned_hello_t * hello) 
.. c:function:: const z_loaned_hello_t * z_hello_loan(const z_owned_hello_t * hello)


Serialization
========================
Types
-----

Represents a data serializer (unstable).
See details at :ref:`owned_types_concept`

.. c:type:: ze_owned_serializer_t
.. c:type:: ze_loaned_serializer_t
.. c:type:: ze_moved_serializer_t

.. autoctype:: serialization.h::ze_deserializer_t

Functions
---------
.. autocfunction:: serialization.h::ze_deserializer_from_bytes
.. autocfunction:: serialization.h::ze_deserializer_deserialize_int8
.. autocfunction:: serialization.h::ze_deserializer_deserialize_int16
.. autocfunction:: serialization.h::ze_deserializer_deserialize_int32
.. autocfunction:: serialization.h::ze_deserializer_deserialize_int64
.. autocfunction:: serialization.h::ze_deserializer_deserialize_uint8
.. autocfunction:: serialization.h::ze_deserializer_deserialize_uint16
.. autocfunction:: serialization.h::ze_deserializer_deserialize_uint32
.. autocfunction:: serialization.h::ze_deserializer_deserialize_uint64
.. autocfunction:: serialization.h::ze_deserializer_deserialize_float
.. autocfunction:: serialization.h::ze_deserializer_deserialize_double
.. autocfunction:: serialization.h::ze_deserializer_deserialize_bool
.. autocfunction:: serialization.h::ze_deserializer_deserialize_slice
.. autocfunction:: serialization.h::ze_deserializer_deserialize_string
.. autocfunction:: serialization.h::ze_deserializer_deserialize_sequence_length
.. autocfunction:: serialization.h::ze_serializer_empty
.. autocfunction:: serialization.h::ze_serializer_finish
.. autocfunction:: serialization.h::ze_serializer_serialize_int8
.. autocfunction:: serialization.h::ze_serializer_serialize_int16
.. autocfunction:: serialization.h::ze_serializer_serialize_int32
.. autocfunction:: serialization.h::ze_serializer_serialize_int64
.. autocfunction:: serialization.h::ze_serializer_serialize_uint8
.. autocfunction:: serialization.h::ze_serializer_serialize_uint16
.. autocfunction:: serialization.h::ze_serializer_serialize_uint32
.. autocfunction:: serialization.h::ze_serializer_serialize_uint64
.. autocfunction:: serialization.h::ze_serializer_serialize_float
.. autocfunction:: serialization.h::ze_serializer_serialize_double
.. autocfunction:: serialization.h::ze_serializer_serialize_bool
.. autocfunction:: serialization.h::ze_serializer_serialize_slice
.. autocfunction:: serialization.h::ze_serializer_serialize_buf
.. autocfunction:: serialization.h::ze_serializer_serialize_string
.. autocfunction:: serialization.h::ze_serializer_serialize_str
.. autocfunction:: serialization.h::ze_serializer_serialize_sequence_length
.. autocfunction:: serialization.h::ze_deserialize_int8
.. autocfunction:: serialization.h::ze_deserialize_int16
.. autocfunction:: serialization.h::ze_deserialize_int32
.. autocfunction:: serialization.h::ze_deserialize_int64
.. autocfunction:: serialization.h::ze_deserialize_uint8
.. autocfunction:: serialization.h::ze_deserialize_uint16
.. autocfunction:: serialization.h::ze_deserialize_uint32
.. autocfunction:: serialization.h::ze_deserialize_uint64
.. autocfunction:: serialization.h::ze_deserialize_float
.. autocfunction:: serialization.h::ze_deserialize_double
.. autocfunction:: serialization.h::ze_deserialize_bool
.. autocfunction:: serialization.h::ze_deserialize_slice
.. autocfunction:: serialization.h::ze_deserialize_string
.. autocfunction:: serialization.h::ze_deserializer_is_done
.. autocfunction:: serialization.h::ze_serialize_int8
.. autocfunction:: serialization.h::ze_serialize_int16
.. autocfunction:: serialization.h::ze_serialize_int32
.. autocfunction:: serialization.h::ze_serialize_int64
.. autocfunction:: serialization.h::ze_serialize_uint8
.. autocfunction:: serialization.h::ze_serialize_uint16
.. autocfunction:: serialization.h::ze_serialize_uint32
.. autocfunction:: serialization.h::ze_serialize_uint64
.. autocfunction:: serialization.h::ze_serialize_float
.. autocfunction:: serialization.h::ze_serialize_double
.. autocfunction:: serialization.h::ze_serialize_bool
.. autocfunction:: serialization.h::ze_serialize_slice
.. autocfunction:: serialization.h::ze_serialize_buf
.. autocfunction:: serialization.h::ze_serialize_string
.. autocfunction:: serialization.h::ze_serialize_str


Others
======

Data Structures
---------------

.. autoctype:: types.h::z_zint_t
   
.. autoctype:: types.h::zp_task_read_options_t
.. autoctype:: types.h::zp_task_lease_options_t
.. autoctype:: types.h::zp_read_options_t
.. autoctype:: types.h::zp_send_keep_alive_options_t
.. autoctype:: types.h::zp_send_join_options_t

Constants
---------

.. autocenum:: constants.h::z_whatami_t

Macros
------
.. autocmacro:: macros.h::z_loan
.. autocmacro:: macros.h::z_move
.. autocmacro:: macros.h::z_clone
.. autocmacro:: macros.h::z_drop
.. autocmacro:: macros.h::z_closure

Functions
---------

.. autocfunction:: primitives.h::zp_task_read_options_default
.. autocfunction:: primitives.h::zp_start_read_task
.. autocfunction:: primitives.h::zp_stop_read_task

.. autocfunction:: primitives.h::zp_task_lease_options_default
.. autocfunction:: primitives.h::zp_start_lease_task
.. autocfunction:: primitives.h::zp_stop_lease_task

.. autocfunction:: primitives.h::zp_read_options_default
.. autocfunction:: primitives.h::zp_read

.. autocfunction:: primitives.h::zp_send_keep_alive_options_default
.. autocfunction:: primitives.h::zp_send_keep_alive
.. autocfunction:: primitives.h::zp_send_join_options_default
.. autocfunction:: primitives.h::zp_send_join

.. TODO Logging
.. TODO =======





