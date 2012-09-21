# Intro to Rspec
by Jon "Lark" Larkowski (l4rk)

## RSpec vs Test::Unit vs minitest

    describe BlogPost do
      describe "#remove!" do
        let(:blog_post) do
          BlogPost.new.tap do |p|
            ...
          end
        end

        context "when it's unpublished" do
          let(:published_at) { nil }

          it "destroys the blog post" do
            blog_post.should_receive(:destroy)
            blog_post.remove!
          end
        end

        context "when it's published" do
          let(:published_at) { Time.now }

          it "raises an error" do
            expects { blog.remove! }.to raise_error(BlogPostNotRemovable)
          end
        end

      end
    end


## Expectations

  * should, should_not
  * matchers: equal, include, raise_error
  * expect{ foo }.to change{ bar }
  * ...


## Mocking & Stubbing
  Stub what you can't control
  Mock what you CAN control

  ! Look up "double"


## View tests

  * When every tag counts


## Controller Specs

  He doesn't write a lot of controller specs since he uses a lot of capybara integration tests.

    describe WidgetsController do
      describe "GET index" do
        it "assigns all widgets to @widgets" do
          widget = stub_model(Widget)
          Widget.stub(:all) { [widget] }
          get :index
          assigns(:widgets).should eq([widget])
        end
      end
    end

    it "does not expose a list of profiles" do
      { :get => "/profiles" }.should_not be_routable
    end

## Request specs

    describe "home page" do
      it "displays the user's useranme after successful login" do
        user = Factory(:user, username: 'jdoe', password: 'secret')
        visit: '/login'
        fill_in 'username', with: 'jdoe'
        fill_in 'password', with: 'secret'
      end
    end


## Questions

  Difference between RSpec vs Mocha

