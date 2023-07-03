Your Notes Here
Add a new toy when the toy form is submitted

How I debugged:

after clicking on the create new toy button got

NameError (uninitialized constant ToysController::Toys):

app/controllers/toys_controller.rb:10:in `create'

in the terminal, then went to toys_controller.rb

and realsied that 

 def create
    toy = Toys.create(toy_params)
    render json: toy, status: :created
  end
  
  should be

  def create
    toy = Toy.create(toy_params)
    render json: toy, status: :created
  end

Update the number of likes for a toy

How I debugged:

i updated the params of the toys_controller.rb

private
  
  def toy_params
    params.permit(:id, :name, :image, :likes)
  end

  it only updates after a page re-load


Donate a toy to Goodwill (and delete it from our database)

How I debugged: I added destroy to the routes resources 