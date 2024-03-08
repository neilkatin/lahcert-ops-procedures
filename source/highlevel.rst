========================
High Level Description
========================

The basics
------------------------

We've had a lot of trouble finding a way to describe the paperwork process that is neither too high level nor too details.

This is another attempt to give an overview.

Assumptions
-----------

This page will talk about submitting an Ops Assignment (described in a later chapter) and how it travels through the system.
We will focus on how an individual request flows from area to area.

All 'forms' described here are on the
`LAH CERT web site <https://cert.lahcfd.org/procedures>`_,
in the `procedures tab <https://cert.lahcfd.org/procedures>`_:
`Ops Forms <https://docs.google.com/spreadsheets/d/1sh4pCOxAvYapsXrGWivghP8bRin9ZeFI6Vdj3jQ3aRY/edit#gid=0>`_

The Phases
----------

You can think about the 'flow' of an ad-hoc request as following these steps:

* initial submission to Ops
* task assignment from Ops to position (typically Recon)
* status updates from position to Ops
* task completion to Ops

Initial Submission
------------------

An ad-hoc task request can come from many places, but it always goes to Ops for prioritization and tracking.

It can come through Recon based on a report from a field team.

It can come from Comms or IT if it came in via email, text, or phone (typically from the EOC, but perhaps from the public)

It could come from check-in if it was submitted by someone walking by the ARK.

In all cases: it goes to Ops as the next step

.. graphviz::

    digraph {
        "EOC" -> "IT";
        "EOC" -> "Comms";
        "Recon" -> "Ops";
        "Comms" -> "Ops";
        "IT" -> "Ops";
        "Anywhere else" -> "Ops";
    }

Ops reviews the request, asks for clarification if necessary, confers with the Incident Commander (IC)
to set priorities, and sends the request to an Ark group to take action.

Typically the group will be Recon, but the group could be Logistics (if something needs to be purchased) or any other Ark group.

Task assignment to a group
--------------------------

.. graphviz::

    digraph {
      "Ops" -> "Logistics" [ style=dotted xlabel="Alternate path" ];
      "Ops" -> "Any other group" [ style=dotted headlabel="Alternate path" ];
      "Ops" -> "Recon" [ label=<&nbsp;    Primary path> ];
      "Ops" -> "IT" [ style=dashed xlabel="To be scanned and shared with EOC" ];
    }

Once a task is assigned to a group: that group is responsible for 'making it happen'.
This example will use Recon as the assigned group, but it applies to all groups.

The first thing to do is to add this task to the Ad Hoc tracking form.

When you assign a task to a team to be worked on: you should update the Ad Hoc tracking form and the Ops Assignment form.

As you receive updates you should update both forms too.

Periodic updates
----------------

Each team with assignments (and Recon with the Preplanned assignments) will periodically
(as determined by Ops and the IC)
send updates Preplanned (Recon only) and Ad Hoc (everyone) tracking sheet.

The model is:

* make a copy of the tracking sheet(s).
* Put the time the copy was made in the upper right of the sheet.
* make a copy and distribute the sheet to the other groups.

    * Ops
    * Scribe
    * IT (who will share with the EOC)
    * (anyone else that Ops says to send status updates to)

.. graphviz::

    digraph {
      Recon [ label="Recon\nand any other group\nwith a task" ];
      Recon -> Ops;
      Recon -> Scribe;
      Recon -> IT;
    }


Task completion
----------------

When a task is complete: update the Ad Hoc tracking sheet and the Ops Assignment form.

Make copies, add a timestamp to the Ad Hoc tracking sheet
(the Ops Assignment already has a completed timestamp),
and distribute just like in the last step.

.. graphviz::

    digraph {
      Recon [ label="Recon\nand any other group\nwith a task" ];
      Recon -> Ops;
      Recon -> Scribe;
      Recon -> IT;
    }

