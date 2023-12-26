---
layout: post
title:  That which does not kill us makes us stronger
description: Sin tantum est boni praeter summam voluptatem, et eam sempiternam. Cur post Tarentum ad Archytam. Qua ex cognitione facilior facta est investigatio rerum occultissimarum, empull...
date:   2018-11-14 15:01:35 +0300
image:  '/images/02.jpg'
tags:   [workflow, hobby, study]
---

Sin tantum est boni praeter summam voluptatem, et eam sempiternam. Cur post Tarentum ad Archytam. Qua ex cognitione facilior facta est investigatio rerum occultissimarum, empulla enim tenuissimo victu, id est contemptissimis escis et potionibus, minorem voluptatem percipi quam rebus exquisitissimis ad epulandum. Non enim iam stirpis bonum quaeret.

<!--more-->

 sed animalis. Qui autem esse poteris, nisi te amor ipse ceperit. Sic igitur in homine perfectio ista in eo potissimum, quod est optimum, id est in virtute, laudatur. Natura sic ab iis investigata est, ut nulla pars caelo, mari, terra, ut poëtice loquar, praetermissa sit. Eadem nunc mea adversum te oratio est. Mihi quidem Homerus huius modi quiddam vidisse videatur in iis, quae de Sirenum cantibus ages tandem finxerit.


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