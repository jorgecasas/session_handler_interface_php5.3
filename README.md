# session_handler_interface_php5.3
PHP 5.3 compatibility for PHP 5.4's \SessionHandlerInterface


## License
This program is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation; either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <http://www.gnu.org/licenses/>.


## Example 

```php

/**
 * SessionHandler class
 * @link http://php.net/manual/en/class.sessionhandler.php
 */
class SessionHandler implements SessionHandlerInterface {
    
    /**
     * Close the session
     * 
     * @return bool The return value (usually TRUE on success, FALSE on failure).
     * 
     * @note This value is returned internally to PHP for processing.
     */
    public function close() {
        return true;
    }

    /**
     * Destroy a session
     *
     * @param int $id The session ID being destroyed.
     * @return bool The return value (usually TRUE on success, FALSE on failure).
     * 
     * @note This value is returned internally to PHP for processing.
     */
    public function destroy($id) {
        return true;
    }

    /**
     * Cleanup old sessions
     *
     * @param   int  $maxlifetime  Sessions that have not updated for the last maxlifetime seconds will be removed.
     * @return  bool  The return value (usually TRUE on success, FALSE on failure).
     * 
     * @note This value is returned internally to PHP for processing.
     */
    public function gc($maxlifetime) {
        return true;
    }

    /**
     * Initialize session
     *
     * @param   string  $savePath  The path where to store/retrieve the session.
     * @param   string  $id        The session id.
     * @return  bool  The return value (usually TRUE on success, FALSE on failure).
     * 
     * @note This value is returned internally to PHP for processing.
     */
    public function open($savePath, $id) {
        return true;
    }

    /**
     * Read session data
     *
     * @param   string  $id  The session id to read data for.
     * @return  string  Returns an encoded string of the read data. If nothing was read, it must return an empty string.
     * 
     * @note This value is returned internally to PHP for processing.
     */
    public function read($id) {
        return null;
    }

    /**
     * Write session data
     *
     * @param   string  $id    The session id.
     * @param   string  $data  The encoded session data. This data is the result of the PHP internally encoding
     *                         the $_SESSION super global to a serialized string and passing it as this parameter.
     *                         Please note sessions use an alternative serialization method.
     *
     * @return   bool  The return value (usually TRUE on success, FALSE on failure).
     * 
     * @note This value is returned internally to PHP for processing.
     */
    public function write($id, $data) {
        return true;
    }
}

// Using the new controller to handle sessions
$session_handler = new SessionHandler();
session_set_save_handler( $session_handler, true );

```

## Composer.json
In order to use composer, complete your composer.json file with:
```js
{
    "require": {
       "vcorbacho/session_handler_interface_php5.3": "dev-master"
    }
}
```





