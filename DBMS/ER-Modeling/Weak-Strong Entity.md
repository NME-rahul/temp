# Weak Entity
An etity is called weak if it can not derive it's all attributes without the help of other entity. basically an entity without primary-key is called weak entityy. Therefore, it must use a foreign-key in conjusction with its attributes to create a primary-key.
Each element in the weak entity set must have a relationship with exactly one element in the parent(strong) entity set.


# Weak relation(identifying realtion)

A weak relation refers the relationship between a weak entity and the strong entity it depends on. This relationship helps in identfying the waek entity since weak entity's identification is partially derived from the strong entity.

<div align="center">
  <img height="" width="" src="https://media.geeksforgeeks.org/wp-content/uploads/Database-Management-System-ER-Model-20.png">
</div>


* **Weak entity(dependants) is refering to the strong(regular) entity by the help of weak relation "has".**
