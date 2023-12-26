---
layout: post
title:  Welcome to my blog site
description: I'm Tapas Datta, a Senior Software Engineer rooted in the vibrant city of Dhaka.
date:   2023-12-26 15:01:35 +0600
image:  '/images/02.jpg'
tags:   [Elixir, Erlang, Tapas]
---

I'm Tapas Datta, a Senior Software Engineer rooted in the vibrant city of Dhaka. My days are immersed in the dynamic world of technology, specializing in the elegant languages of Erlang & Elixir. I pursued both a Bachelor's and Master's degree in Computer Science and Engineering. Passion for Software Architecture and AI runs deep in my veins.
<!--more-->
I'm deeply engrossed in crafting robust software solutions, bringing my technical expertise to the forefront. However, my love for coding extends beyond the confines of the conventional workday. In my spare time, I dedicate at least 1 to 2 hours daily to the world of open-source projects, contributing to the thriving community that fuels innovation and collaboration.

But life isn't all about lines of code. In the quiet moments, you'll find me nose-deep in books, savoring the wisdom they hold, and soaking in the melody of music :musical_note: that accompanies my journey. This blog is a reflection of my tech-driven world and a canvas for the stories I unravel.

Here, in this blog, I navigate the realms of programming, share my learnings, and explore the limitless possibilities that the world of software engineering offers. Whether you're a fellow coder, an enthusiast, or simply curious about the tech universe, welcome to a place where bytes and bits come to life! 


{% highlight elixir exs %}
defmodule Whisper.Albums.Album do
  use Ecto.Schema
  import Ecto.Changeset

  schema "albums" do
    field :title, :string

    timestamps(type: :utc_datetime)

  end

  @doc false
  def changeset(album, attrs) do
    album
    |> cast(attrs, [:title])
    |> validate_required([:title])
    |> validate_length(:title, min: 3, max: 20)
  end
end

{% endhighlight %}