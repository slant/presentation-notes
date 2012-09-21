# Testing

http://bit.ly/rtfz2012

Check for migrations and prepare database
rake db:test:prepare

Run tests
rake test
rake

Run an individual test
ruby -Itest test/unit/zombie_test.rb

Run an individual test case
ruby -Itest test/unit/zombie_test.rb -n test_the_truth

Responding to methods
assert_respond_to instance, instance_method_name
assert_respond_to class, class_method_name

def test_..._valid
test '... valid' do (different DSL)


## Cleaning up

### Setup

  def setup
    @z = zombies(:ash)
  end

  test "should do a thing" do
    assert @z
  end


## Refactoring our Tests

    class ActiveSupport::TestCase
      def assert_presence(model, field)
        model.valid?
        assert_match /can't be blank/, model.errors[field].join,
          "Presence error for #{field} not found on #{model.class}"
      end
    end

    test "invalid name gives error message" do
      @z.name = nil
      assert_presence(@z, :name)
    end


## Shoulda

  Shoulda has pre-built methods like this previous one.

    group :test do
      gem 'shoulda'
    end

    class ZombieTest < ActiveSupport::TestCase
      should validate_presence_of(:name)
      should validate_presence_of(:graveyard)
      should ensure_length_of(:name).is_at_most(15)
      should have_many(:tweets)

      should validate_uniqueness_of(:name)
      should ensure_length_of(:password).is_at_least(5).is_at_most(20)
      should_not allow_value('blah').for(:email)
      should_now allow_mass_assignment_of(:password)
      should validate_acceptance_of
    end


## Stubs vs Mocks

  Stub
    For replacing a method with code that returns a specified result.

  Mock
    A stub with an assertion that the method gets called.


  



## Notes

  You should never test Rails.
  But you should always test your business rules.

  There are people who test too far or too deep into associations, for
example.


