magic_model
============

Smarter Python Data Models


* aware of data store. If SQL, table/column does not exist it creates it. Can also store unknown attributes in json columns. If NoSQL, then it is smart enough to save as is.
* goes to and from json seemlessly
* Can be created/updated from dict or attributes
* validation... is valid
* Aware of changed fields and previous values
* Based on Models from Backbone js


```python

class MagicModel:
  
  changed = {}
  attributes = {}
  defaults = {}
  validation_errors = []
  id_attribute = 'id'

  # Create a new model with the specified attributes. 
  def __init( self, attributes, options )__:
    # apply defaults 
    # apply attributes
    # set changed to {}
    pass    
    
  # Return a copy of the model's `attributes` dict
  def to_json( self ):
    pass

  # sync to datastore
  def sync( self ):
    pass
    
  # Get the value of an attribute.
  def get( self, attr ):
    pass
  
  # Returns `true` if the attribute contains a value that is not null
  # or undefined.
  def has( self, attr ):
    pass
    
  # Set a hash of model attributes on the object
  def set( self, key, val, options ):
    pass
    
  # Remove an attribute from the model  
  def unset( self, attr ):
    pass
  
  # Clear all attributes on the model  
  def clear( self ):
    pass
    
  # Determine if the model has changed since the last `"change"` event.
  # If you specify an attribute name, determine if that attribute has changed.    
  def has_changed( self, attr = None ):
    pass

  # Return an object containing all the attributes that have changed, or
  # false if there are no changed attributes. 
  # You can also pass an attributes object to diff against the model,
  # determining if there *would be* a change.
  def changedAttributes( self, diff = None ):
    pass

  # Get the previous value of an attribute, recorded at the time the last
  # `"change"` event was fired.
  def previous( self, attr = None ):
    pass

  # Get all of the attributes of the model at the time of the previous
  # `"change"` event.
  def previous_attributes( self ):
    pass
    
  # Fetch the model from the server. If the server's representation of the
  # model differs from its current attributes, they will be overridden,    
  def fetch( self ): 
    pass

  # Set a hash of model attributes, and sync the model to the server.
  # If the server returns an attributes hash that differs, the model's
  # state will be `set` again.
  def save( self ):
    pass

  # Destroy this model on the server if it was already persisted.
  def destroy( self ):
    pass

  # **parse** converts a response into the hash of attributes to be `set` on
  # the model. The default implementation is just to pass the response along.
  def parse( self, json ):
    pass

  # Create a new model with identical attributes to this one.
  def clone( self ): 
    pass

  # A model is new if it has never been saved to the server, and lacks an id.
  def isNew( self ): 
    pass

  # Run validation against the next complete set of model attributes,
  # returning `true` if all is well. Otherwise, fire an `"invalid"` event.  
  def validate( self, attrs ):  
    pass

  # Check if the model is currently in a valid state
  def is_valid( self ):  
    pass

    
```
