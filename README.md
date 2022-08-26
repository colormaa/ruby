# README

This README would normally document whatever steps are necessary to get the
application up and running.

Things you may want to cover:

* Ruby version

* System dependencies

* Configuration

* Database creation

* Database initialization

* How to run the test suite

* Services (job queues, cache servers, search engines, etc.)

* Deployment instructions

* ...

 > rails g scaffold post title:string body:text
 > bundle add rack-cors
 > rails db:migrate

 ======================
 > touch /config/initialers/cors.rb
 in that 



 ---start ----
 Rails.application.config.middleware.insert_before 0, Rack::Cors do
    allow do
        origins '*'
        resource '*', headers: :any, methods: %i[get post patch put delete]
    end
end
---- end----
=====================

in app/controllers/posts_controller.rb

in post_params 
add :id 
in params ( :title, :body, :id)
===================

at the top 
class PostsController < ApplicationController
  before_action :set_post, only: %i[ show edit update destroy ]
  + skip_before_action :verify_authenticity_token
========================
  change delete section 
  # DELETE /posts/1 or /posts/1.json
  def destroy
    @post.destroy

    respond_to do |format|
      format.html { redirect_to posts_url, notice: "Post was successfully destroyed." }
      * format.json { render json: Post.all, status:  :ok}

=======
in blog folder create frontend react proejct
> npx create-react-app frontend --template redux-typescript

in frontend public head section add 
bootsraop 5 css cdn

<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC" crossorigin="anonymous">

and bundle js cdn 
<script src="https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js" integrity="sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM" crossorigin="anonymous"></script>
==================

in src App.tsx

import React from 'react';
import './App.css';

function App() {
  return (
    <div className="App">
      
    </div>
  );
}

export default App;
