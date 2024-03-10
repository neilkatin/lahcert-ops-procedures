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

All Ops forms described here are on the
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

An incident notification to Ops can come from many different places (Recon, Comms, Check-in, etc) and in many different ways
(`an LAH-102 Incident form <https://drive.google.com/file/d/1sztzAOLeT6FsNXa7MY3fJe20u9R9T4tA/view?usp=drive_link>`_,
`an ICS-213 Message Form <https://www.scc-ares-races.org/operations/forms/go-kit/ICS-213_SCCo_Message_Form_Fillable_v20220119.pdf>`_,
a plain sheet of paper [aka Form 1], or verbally without anything in writing)

.. graphviz::

    digraph {
        "EOC" -> "IT";
        "EOC" -> "Comms";
        "Recon" -> "Ops";
        "Comms" -> "Ops";
        "IT" -> "Ops";
        "Anywhere else" -> "Ops";
    }

In all cases Ops needs to decide what action (if any) we should take.

Task assignment to a group
--------------------------

Ops reviews the notification, asks for clarification if necessary, confers with the Incident Commander (IC)
to set priorities, and generates an Ops Assignment form if Ops wants CERT to take action.  Ops should attach any additional information (such as an incident form) to the Ops Assignment if the incident form adds useful information.

Typically the group will be Recon, but the group could be Logistics (if something needs to be purchased) or any other Ark group.

.. graphviz::

    digraph {
      "Ops" -> "Logistics" [ style=dotted xlabel="Alternate path" ];
      "Ops" -> "Any other group" [ style=dotted headlabel="Alternate path" ];
      "Ops" -> "Recon" [ label=<&nbsp;    Primary path> ];
      "Ops" -> "Planning/Scribe" [ style=dashed label="to update status board" ]
      "Ops" -> "IT" [ style=dashed xlabel="To be scanned and shared with EOC" ];
    }

Once a task is assigned to a group: that group is responsible for 'making it happen'.
This example will use Recon as the assigned group, but it applies to all groups.

The first thing to do is to add this task to the Ad Hoc tracking form.

When you assign a task to a team to be worked on: you should update the Ad Hoc tracking form and the Ops Assignment form.

As the team with the assigned task receives updates they should update both forms too.

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
    * Planning/Scribe
    * IT (who will share with the EOC)
    * (anyone else that Ops says to send status updates to)

.. graphviz::

    digraph {
      Recon [ label="Recon\nand any other group\nwith a task" ];
      Recon -> Ops;
      Scribe [ label="Planning/Scribe" ];
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
      Scribe [ label="Planning/Scribe" ];
      Recon -> Scribe;
      Recon -> IT;
    }

