# Restaurant-Bot
{
  "intents": [
    {
      "intent": "enquiry",
      "examples": [
        {
          "text": "can you provide me with menu"
        },
        {
          "text": "do you have any offers"
        },
        {
          "text": "i want to look into the menu"
        },
        {
          "text": "what are the offers available"
        },
        {
          "text": "what are the special items in the menu"
        }
      ],
      "description": ""
    },
    {
      "intent": "Greeting",
      "examples": [
        {
          "text": "Good Afternoon"
        },
        {
          "text": "Good Evening"
        },
        {
          "text": "Good Morning"
        },
        {
          "text": "Hello"
        },
        {
          "text": "Hi"
        }
      ],
      "description": ""
    },
    {
      "intent": "order",
      "examples": [
        {
          "text": "can you please take the order"
        },
        {
          "text": "i want to place an order"
        }
      ],
      "description": ""
    }
  ],
  "entities": [
    {
      "entity": "email",
      "values": [
        {
          "type": "patterns",
          "value": "email",
          "patterns": [
            "\\b[A-Za-z0-9._%+-]+@([A-Za-z0-9-]+\\.)+[A-Za-z]{2,}\\b"
          ]
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "enquiry",
      "values": [
        {
          "type": "synonyms",
          "value": "menu",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "offers",
          "synonyms": [
            "deals",
            "discounts"
          ]
        },
        {
          "type": "synonyms",
          "value": "special items",
          "synonyms": [
            "specials"
          ]
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "greetings",
      "values": [
        {
          "type": "synonyms",
          "value": "Good Afternoon",
          "synonyms": [
            "ga",
            "gud evng"
          ]
        },
        {
          "type": "synonyms",
          "value": "Good Evening",
          "synonyms": [
            "ge",
            "gud aftn"
          ]
        },
        {
          "type": "synonyms",
          "value": "Good Morning",
          "synonyms": [
            "gm",
            "gud mrng"
          ]
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "items",
      "values": [
        {
          "type": "synonyms",
          "value": "Chicken Biryani",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Chicken Wings",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Chilli Egg",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Paneer Masala",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Veg Noodles",
          "synonyms": []
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "order",
      "values": [
        {
          "type": "synonyms",
          "value": "order",
          "synonyms": [
            "buy",
            "orders",
            "purchase"
          ]
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "payment",
      "values": [
        {
          "type": "synonyms",
          "value": "Card",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "COD",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "UPI",
          "synonyms": []
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "Specials",
      "values": [
        {
          "type": "synonyms",
          "value": "Chicken Wings",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Chilli Egg",
          "synonyms": []
        },
        {
          "type": "synonyms",
          "value": "Paneer Masala",
          "synonyms": []
        }
      ],
      "fuzzy_match": true
    },
    {
      "entity": "sys-number",
      "values": [],
      "fuzzy_match": true
    }
  ],
  "metadata": {
    "api_version": {
      "major_version": "v2",
      "minor_version": "2018-11-08"
    }
  },
  "dialog_nodes": [
    {
      "type": "standard",
      "title": "Anything else",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "I didn't understand. You can try rephrasing."
              },
              {
                "text": "Can you reword your statement? I'm not understanding."
              },
              {
                "text": "I didn't get your meaning."
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "conditions": "anything_else",
      "dialog_node": "Anything else",
      "previous_sibling": "node_8_1617950358321",
      "disambiguation_opt_out": true
    },
    {
      "type": "event_handler",
      "parent": "node_8_1617950358321",
      "event_name": "focus",
      "dialog_node": "handler_1_1617950708040",
      "previous_sibling": "node_9_1617951626721"
    },
    {
      "type": "event_handler",
      "output": {
        "text": {
          "values": [
            "How many do you want?"
          ],
          "selection_policy": "sequential"
        }
      },
      "parent": "slot_4_1617951122452",
      "event_name": "focus",
      "dialog_node": "handler_1_1617951122453",
      "previous_sibling": "handler_7_1617951122453"
    },
    {
      "type": "event_handler",
      "output": {
        "text": {
          "values": [
            "We are accepting COD, Card, UPI, What is your mode of payment ?"
          ],
          "selection_policy": "sequential"
        }
      },
      "parent": "slot_2_1617951167623",
      "event_name": "focus",
      "dialog_node": "handler_2_1617951167624",
      "previous_sibling": "handler_7_1617951167624"
    },
    {
      "type": "event_handler",
      "output": {
        "text": {
          "values": [
            "Can you provide me the item you want?"
          ],
          "selection_policy": "sequential"
        }
      },
      "parent": "slot_10_1617950708868",
      "event_name": "focus",
      "dialog_node": "handler_5_1617950708889",
      "previous_sibling": "handler_6_1617950708889"
    },
    {
      "type": "event_handler",
      "output": {},
      "parent": "slot_10_1617950708868",
      "context": {
        "items": "@items"
      },
      "conditions": "@items",
      "event_name": "input",
      "dialog_node": "handler_6_1617950708889"
    },
    {
      "type": "event_handler",
      "output": {},
      "parent": "slot_4_1617951122452",
      "context": {
        "number": "@sys-number"
      },
      "conditions": "@sys-number",
      "event_name": "input",
      "dialog_node": "handler_7_1617951122453"
    },
    {
      "type": "event_handler",
      "output": {},
      "parent": "slot_2_1617951167623",
      "context": {
        "payment": "@payment"
      },
      "conditions": "@payment",
      "event_name": "input",
      "dialog_node": "handler_7_1617951167624"
    },
    {
      "type": "standard",
      "title": "email",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Thank you for giving your email ID. your mail id $email is used for further reference."
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "Welcome",
      "context": {
        "email": "@email.literal"
      },
      "conditions": "@email",
      "dialog_node": "node_1_1617952731242"
    },
    {
      "type": "standard",
      "title": "Specials",
      "parent": "node_7_1617948369372",
      "metadata": {
        "_customization": {
          "mcr": true
        }
      },
      "conditions": "@Specials",
      "dialog_node": "node_2_1617949701821"
    },
    {
      "type": "standard",
      "title": "Enquiry",
      "metadata": {
        "_customization": {
          "mcr": true
        }
      },
      "conditions": "#enquiry || @enquiry",
      "dialog_node": "node_7_1617948369372",
      "previous_sibling": "node_8_1617946927082"
    },
    {
      "type": "standard",
      "title": "Greetings",
      "metadata": {
        "_customization": {
          "mcr": true
        }
      },
      "conditions": "#Greeting || @greetings",
      "dialog_node": "node_8_1617946927082",
      "previous_sibling": "Welcome"
    },
    {
      "type": "frame",
      "title": "Order",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Thank you, your order of $number plates of $items is placed. Please pay using $payment . your receipt is sent to $email"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "next_step": {
        "behavior": "skip_user_input"
      },
      "conditions": "#order && @order:order",
      "dialog_node": "node_8_1617950358321",
      "previous_sibling": "node_7_1617948369372"
    },
    {
      "type": "standard",
      "title": "Deleting Context",
      "output": {
        "deleted": "<?context.remove('items')?><?context.remove('number')?><?context.remove('payment')?><?context.remove('email')?>",
        "generic": [
          {
            "values": [],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_8_1617950358321",
      "conditions": "true",
      "dialog_node": "node_9_1617951626721"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Good Evening!! How can I help you ?"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_8_1617946927082",
      "conditions": "@greetings:(Good Evening)",
      "dialog_node": "response_1_1617947523404",
      "previous_sibling": "response_5_1617947383181"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "It cost of 200/- per plate."
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_2_1617949701821",
      "conditions": "@Specials:(Paneer Masala)",
      "dialog_node": "response_2_1617949824781",
      "previous_sibling": "response_6_1617949790955"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Good Afternoon!! How can I help you ?"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_8_1617946927082",
      "conditions": "@greetings:(Good Afternoon)",
      "dialog_node": "response_3_1617947548544",
      "previous_sibling": "response_1_1617947523404"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "It cost of 150/- per plate."
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_2_1617949701821",
      "conditions": "@Specials:(Chilli Egg)",
      "dialog_node": "response_3_1617949842402",
      "previous_sibling": "response_2_1617949824781"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "We are having 20% off on Vegetarian foods"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          },
          {
            "values": [
              {
                "text": "We are having 10% discount on fastfood"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          },
          {
            "values": [
              {
                "text": "We are having 50% off on Biryani"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_7_1617948369372",
      "conditions": "@enquiry:offers",
      "dialog_node": "response_4_1617948859268",
      "previous_sibling": "response_8_1617948539941"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "title": "Special Items",
            "options": [
              {
                "label": "Chicken Wings",
                "value": {
                  "input": {
                    "text": "Chicken Wings"
                  }
                }
              },
              {
                "label": "Paneer Masala",
                "value": {
                  "input": {
                    "text": "Paneer Masala"
                  }
                }
              },
              {
                "label": "Chilli Egg",
                "value": {
                  "input": {
                    "text": "Chilli Egg"
                  }
                }
              }
            ],
            "response_type": "option"
          }
        ]
      },
      "parent": "node_7_1617948369372",
      "conditions": "@enquiry:(special items)",
      "dialog_node": "response_4_1617949187815",
      "previous_sibling": "response_4_1617948859268"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Good Morning!! How can I help you ?"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_8_1617946927082",
      "conditions": "@greetings:(Good Morning)",
      "dialog_node": "response_5_1617947383181"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "It cost of 250/- per plate."
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "parent": "node_2_1617949701821",
      "conditions": "@Specials:(Chicken Wings)",
      "dialog_node": "response_6_1617949790955"
    },
    {
      "type": "response_condition",
      "output": {
        "generic": [
          {
            "title": "Menu",
            "source": "https://im1.dineout.co.in/images/uploads/restaurant/sharpen/4/j/o/m41327-15239489375ad59d896b40e.jpg",
            "response_type": "image"
          }
        ]
      },
      "parent": "node_7_1617948369372",
      "conditions": "@enquiry:menu",
      "dialog_node": "response_8_1617948539941",
      "previous_sibling": "node_2_1617949701821"
    },
    {
      "type": "slot",
      "parent": "node_8_1617950358321",
      "variable": "$items",
      "dialog_node": "slot_10_1617950708868",
      "previous_sibling": "handler_1_1617950708040"
    },
    {
      "type": "slot",
      "parent": "node_8_1617950358321",
      "variable": "$payment",
      "dialog_node": "slot_2_1617951167623",
      "previous_sibling": "slot_4_1617951122452"
    },
    {
      "type": "slot",
      "parent": "node_8_1617950358321",
      "variable": "$number",
      "dialog_node": "slot_4_1617951122452",
      "previous_sibling": "slot_10_1617950708868"
    },
    {
      "type": "standard",
      "title": "Welcome",
      "output": {
        "generic": [
          {
            "values": [
              {
                "text": "Hello, I am Restaurant bot, How can I help you, please provide your email ID ?"
              }
            ],
            "response_type": "text",
            "selection_policy": "sequential"
          }
        ]
      },
      "conditions": "welcome",
      "dialog_node": "Welcome"
    }
  ],
  "counterexamples": [],
  "system_settings": {
    "off_topic": {
      "enabled": true
    },
    "disambiguation": {
      "prompt": "Did you mean:",
      "enabled": true,
      "randomize": true,
      "max_suggestions": 5,
      "suggestion_text_policy": "title",
      "none_of_the_above_prompt": "None of the above"
    },
    "system_entities": {
      "enabled": true
    },
    "human_agent_assist": {
      "prompt": "Did you mean:"
    },
    "intent_classification": {
      "training_backend_version": "v2"
    },
    "spelling_auto_correct": true
  },
  "learning_opt_out": false,
  "name": "Restaurant Bot",
  "language": "en",
  "description": ""
}
