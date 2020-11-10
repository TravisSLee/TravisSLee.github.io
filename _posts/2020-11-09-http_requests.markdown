---
layout: post
title:      "HTTP Requests"
date:       2020-11-09 21:56:30 -0500
permalink:  http_requests
---


HTTP, or Hypertext Transfer Protocol, is a client-server protocol,  that allows data exchange on the Web.  A client-server protocol are requests are initiated by the recipient, usually a Web browser like Chrome. Clients and servers communicate through exchanging inidividual messages . The messages sent by the client are called requests and the messages sent by the server as an answer are called responses. HTTP request verbs indicate the action to be perform on a given resource. 

The first HTTP request verb I'll go over is GET. The GET verb is used to retrieve, or read, a representation of a resource. We only use GET to read data and we never use it to change said data. An example of this would be in the code snippet directly below. 

```
get '/signup' do
    if !logged_in?
      erb :'/users/signup'
    else
      redirect to '/bbts'
    end
  end
```

Here we are just retrieving data from our servers wheter we are logged in or not.

The next HTTP request verb I'll go over is POST. The POST verb is what we usually use to create new resources. The method requests the server to accept the new instance of the resource. An example of this would be in the code snippet directly below. 

```
 post '/bbts' do
     @bbt = current_user.bbts.build(name: params[:name])
     @bbt.save
     if @bbt.save
       redirect to "/bbts/#{@bbt.id}"
     else
       redirect '/bbts/new'
     end
  end
```

Here we are saying once an instance of a bubbletea is created, we save it, and store it within the user data. Then once it is saved, we redirect to that bubbletea's show page.

Next we have the PUT/PATCH HTTP verbs. Both these verbs are used to modify the resource. The only difference is that PUT usually completely changes the resource, while PATCH only slightly modifies the resource. An example of this would be in the code snippet directly below. 

```
patch '/bbts/:id' do
      @bbt = current_user.bbts.find_by_id(params[:id])
        if @bbt.update(bubble: params[:bubble], brand: params[:brand], sugar_amount: params[:sugar_amount], size: params[:size], temp: params[:temp])
          redirect to "/bbts/#{@bbt.id}"
        else
          redirect to "/bbts/#{@bbt.id}/edit"
        end
```

In this snippet of code,  the PATCH verb finds the bubbletea by id, then updates its attributes and redirects you to the show page. And if the PATCH is unsuccucessful, we are rediected to the edit page.

Finally we have the DELETE verb. Its function is to request the server to delete a resource.  An example of this would be in the code snippet directly below. 
```
 delete '/bbts/:id' do
      @bbt = current_user.bbts.find(params[:id])
      if @bbt
        @bbt.destroy
        redirect to '/bbts'
      else
        redirect '/bbts'
      end
  end
```

So this snippet states after we find the bubbletea by id, we delete it along with its id and we get redirected to the '/bbts' route. Elsewise, we still get redirected to the '/bbts' route.

So in conculsion, the browser sends a HTTP request to the server for a particle resource. The server analyzes  the message, then server sends back a response. Finally, this response contains status information about the request.

