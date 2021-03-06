--------------------
Wrench\\Frame\\Frame
--------------------

.. php:namespace: Wrench\\Frame

.. php:class:: Frame

    Represents a WebSocket frame

    .. php:attr:: length

        The frame data length

    .. php:attr:: type

        The type of this payload

    .. php:attr:: buffer

        The buffer

        May not be a complete payload, because this frame may still be receiving
        data. See

    .. php:attr:: payload

        The enclosed frame payload

        May not be a complete payload, because this frame might indicate a
        continuation frame. See isFinal() versus isComplete()

    .. php:method:: getLength()

        Gets the length of the payload

        :returns: int

    .. php:method:: encode(string $data, int $type = , boolean $masked = )

        Resets the frame and encodes the given data into it

        :param string $data:
        :param int $type:
        :param boolean $masked:
        :returns: Frame

    .. php:method:: isFinal()

        Whether the frame is the final one in a continuation

        :returns: boolean

    .. php:method:: getType()

        :returns: int

    .. php:method:: decodeFramePayloadFromBuffer()

        Decodes a frame payload from the buffer

        :returns: void

    .. php:method:: getExpectedBufferLength()

        Gets the expected length of the buffer once all the data has been
        receieved

        :returns: int

    .. php:method:: isComplete()

        Whether the frame is complete

        :returns: boolean

    .. php:method:: receiveData($data)

        Receieves data into the frame

        :param unknown $data:

    .. php:method:: getRemainingData()

        Gets the remaining number of bytes before this frame will be complete

        :returns: number

    .. php:method:: isWaitingForData()

        Whether this frame is waiting for more data

        :returns: boolean

    .. php:method:: getFramePayload()

        Gets the contents of the frame payload

        The frame must be complete to call this method.

        :returns: string

    .. php:method:: getFrameBuffer()

        Gets the contents of the frame buffer

        This is the encoded value, receieved into the frame with recieveData().

        :returns: string binary

    .. php:method:: getBufferLength()

        Gets the expected length of the frame payload

        :returns: int
